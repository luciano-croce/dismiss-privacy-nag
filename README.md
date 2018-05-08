# Dismiss Privacy Nag

Dismiss Privacy and Personal Data Dashboard Nag Pointer Tooltip Notification, when it is activated, or if it is in mu-plugins.

Why this plugin?

Seem that the new privacy pointer is not "totally" auto dismissible when is clicked one of the admin menu links, for example:

 * If one of the any admin menu links was clicked, the privacy pointer disappear.
 * If the dasboard admin menu link was clicked, the privacy pointer not disappear, return visible, and nagging user.
 * The [privacy pointer is misaligned to admin menu](https://core.trac.wordpress.org/ticket/43996/) when exist other admin menu items of 3rd party: 
 * The suggested code to auto dismiss it seem to not working well.
 
<code>remove_action( 'admin_print_footer_scripts', array( 'WP_Internal_Pointers', 'pointer_wp496_privacy' ) );</code>

Based to the [Detailed Guidelines 11](https://developer.wordpress.org/plugins/wordpress-org/detailed-plugin-guidelines/#12-public-facing-pages-on-wordpress-org-readmes-must-not-spam): plugins should not hijack the admin dashboard. 

 * Users prefer and expect plugins to feel like part of WordPress.
 * Constant nags and overwhelming the admin dashboard with unnecessary alerts detract from this experience.
 * Upgrade prompts, notices, alerts, and the like must be limited in scope and used sparingly, be that contextually or only on the plugin’s setting page.
 * Site wide notices or embedded dashboard widgets must be dismissible or self-dismiss when resolved.
 * Error messages and alerts must include information on how to resolve the situation, and remove themselves when completed.

Privacy: Add an admin pointer for new privacy features in 4.9.6.

 * The new features are very important for some users, because of their GDPR obligations.
 * They're also spread across multiple top-level menus, making them less discoverable.
 * An admin pointer will help to ensure that users are aware of the new tools and how to find them.

Props desrosj, andreamiddleton, allendav, xkon.
Fixes #43942 ?

 * [4.9.6-alpha-43159](https://build.trac.wordpress.org/browser/branches/4.9?rev=42988)
 * [4.9.6-alpha-42959-src](https://core.trac.wordpress.org/browser/branches/4.9?rev=43159)
 * [5.0-alpha-43158](https://build.trac.wordpress.org/browser/trunk?rev=42987)
 * [5.0-alpha-42970-src](https://core.trac.wordpress.org/browser/trunk?rev=43158)

Dismiss all the new feature pointers.

@since 3.3.0

All pointers can be disabled using the following:

<code>remove_action( 'admin_enqueue_scripts', array( 'WP_Internal_Pointers', 'enqueue_scripts' ) );</code>

@param string $hook_suffix The current admin page.

Dismiss a pointer for the new privacy tools.

@since 4.9.6

Privacy pointer can be disabled using the following:

<code>remove_action( 'admin_print_footer_scripts', array( 'WP_Internal_Pointers', 'pointer_wp496_privacy' ) );</code>

@param string $hook_suffix The current admin page.
