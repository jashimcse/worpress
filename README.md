index.php file task
<a><img src="<?php echo get_template_directory_uri() ?>/assets/images/twitter-blue-icon.png"></a>

for nav
 <?php
                                wp_nav_menu(
                                  array(
                                    'theme_location' => 'menu-1',
                                    'menu_id'        => 'primary-menu',
                                    'menu_class'        => 'navbar-nav custom_nav',
                                  
                                  )
                                );
                                ?>
                                
                                for dynamic sideber
                                <?php dynamic_sidebar('banner')?> </a>
                                for footer
                                <?php wp_footer();?>
                                for  header
                                
                                   <?php wp_head();?>
                                   
                                   functions.php task
                                   
  define( 'WP_DEBUG', true );

if ( ! defined( '_S_VERSION' ) ) {
	// Replace the version number of the theme on each release.
	define( '_S_VERSION', '1.0.0' );
}
function jashimcse_setup() {
	/*
		* Make theme available for translation.
		* Translations can be filed in the /languages/ directory.
		* If you're building a theme based on Jashimcse, use a find and replace
		* to change 'jashimcse' to the name of your theme in all the template files.
		*/
	load_theme_textdomain( 'jashimcse', get_template_directory() . '/languages' );
}



function jashimcse_scripts() {
	wp_enqueue_style( 'jashimcse-style', get_stylesheet_uri(), array(), _S_VERSION );
	wp_enqueue_style( 'jashimcse-style-bootstrap', get_template_directory_uri().'/assets/css/bootstrap.min.css', array(), _S_VERSION );
	// wp_style_add_data( 'jashimcse-style', 'rtl', 'replace' );

	wp_enqueue_script( 'jashimcse-navigation', get_template_directory_uri().'/assets/js/bootstrap.bundle.min.js', array(), _S_VERSION, true );

	// if ( is_singular() && comments_open() && get_option( 'thread_comments' ) ) {
	// 	wp_enqueue_script( 'comment-reply' );
	// }
    
}
add_action( 'wp_enqueue_scripts', 'jashimcse_scripts' );


/**
	 * Add support for core custom logo.
	 *
	 * @link https://codex.wordpress.org/Theme_Logo
	 * 
	 */
	
	add_theme_support(
		'custom-logo',
		array(
			'height'      => 250,
			'width'       => 250,
			'flex-width'  => true,
			'flex-height' => true,
		)
	);
	
	// This theme uses wp_nav_menu() in one location.
	register_nav_menus(
		array(
			'menu-1' => esc_html__( 'Primary', 'jashimcse' ),
			'menu-2' => esc_html__( 'Footer', 'jashimcse' ),
		)
	);

add_action( 'after_setup_theme', 'jashimcse_setup' );


?>
                                   
                                   
                                   
                            
