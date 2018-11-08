<?php
/*
Plugin Name: RestAPI Full Path
Description: WP Rest API - Retrieve sub page by full slug (URL/Path)
Author: raNikola
Author URI: http://ranikola.iz.rs
 */

add_filter( "rest_page_collection_params", 'collectionParams', 20, 2 );
function collectionParams($query_params, $post_type) {
    $query_params['slug']['sanitize_callback'] = 'parse_slug_list';
    return $query_params;
}

function parse_slug_list($list) {
    if ( !is_array( $list ) ) {
        $list = preg_split( '/[\s,]+/', $list );
    }
    $listArray = array_filter( explode( '/', $list[0]), 'strlen' );

    return array_values(array_slice($listArray, -1));
}
