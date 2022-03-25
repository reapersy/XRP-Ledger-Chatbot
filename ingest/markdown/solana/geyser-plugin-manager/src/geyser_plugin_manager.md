[View code on GitHub](https://github.com/solana-labs/solana/blob/master/geyser-plugin-manager/src/geyser_plugin_manager.rs)

The `GeyserPluginManager` struct in this file manages the Geyser plugins used in the larger project. It contains a vector of `Box<dyn GeyserPlugin>` objects, which are plugins that implement the `GeyserPlugin` trait defined in the `solana_geyser_plugin_interface` crate. The `libs` vector contains dynamically linked libraries that are loaded when plugins are loaded.

The `new` method creates a new `GeyserPluginManager` instance with empty vectors for plugins and libraries.

The `load_plugin` method loads a plugin from a dynamically linked library specified by `libpath`. It uses the `libloading` crate to load the library and retrieve a constructor function named `_create_plugin`. This function creates a raw pointer to a `GeyserPlugin` object, which is then converted to a boxed object and added to the `plugins` vector. The `on_load` method of the plugin is called with the `config_file` parameter to perform any necessary initialization. If loading the plugin fails, an error is returned.

The `unload` method unloads all plugins and their associated libraries. It calls the `on_unload` method of each plugin to perform any necessary cleanup.

The `account_data_notifications_enabled` and `transaction_notifications_enabled` methods check if any loaded plugins are interested in receiving notifications for account data or transaction data, respectively. They iterate over the `plugins` vector and call the corresponding methods on each plugin. If 