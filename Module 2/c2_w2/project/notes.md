def paginated_new_releases(endpoint_request: Callable, url: str, access_token: str, offset: int=0, limit: int=20) -> list:
    responses = []
    
    # Create a dictionary named kwargs with the values
    kwargs = { 
        "url": url,
        "access_token": access_token,
        "offset": offset,
        "limit": limit,
    } 

    # Call the endpoint_request() function with the arguments
    response = endpoint_request(**kwargs)
    # Use extend() method to add the albums' items to the list
    responses.extend(response.get('albums').get('items'))
    # Get the total number of elements
    total_elements = response.get('albums').get('total')

    # Run the loop as long as offset is smaller than total_elements
    while offset < total_elements:
        # Update the offset value
        offset = response.get('albums').get('offset') + limit
        # Update the offset in kwargs
        kwargs["offset"] = offset
        
        # Call the endpoint_request() function again
        response = endpoint_request(**kwargs)
        # Extend responses with new items
        responses.extend(response.get('albums').get('items'))
        
        print(f"Finished iteration for page with offset: {offset-limit}")

    return responses


    def paginated_new_releases_sdk(limit: int=20) -> list:
    album_data = []
    
    # First request
    response = spotify.new_releases(limit=limit)
    # Extend with first page items
    album_data.extend(response.get('albums').get('items'))
    # Get total elements
    total_albums_elements = response.get('albums').get('total')
    # Create offset list (start at limit, end at total, step by limit)
    offset_idx = list(range(limit, total_albums_elements, limit))

    for idx in offset_idx:
        # Request with offset
        response_page = spotify.new_releases(limit=limit, offset=idx)
        # Extend with page items
        album_data.extend(response_page.get('albums').get('items'))
    
    return album_data