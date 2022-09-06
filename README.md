# Ad
struct audio_hw_device {     struct hw_device_t common;      /**      * used by audio flinger to enumerate what devices are supported by      * each audio_hw_device implementation.      *      * Return value is a bitmask of 1 or more values of audio_devices_t      */     uint32_t (*get_supported_devices)(const struct audio_hw_device *dev);   ... }; typedef struct audio_hw_device audio_hw_device_t;
struct audio_hw_device {
    struct hw_device_t common;

    /**
     * used by audio flinger to enumerate what devices are supported by
     * each audio_hw_device implementation.
     *
     * Return value is a bitmask of 1 or more values of audio_devices_t
     */
    uint32_t (*get_supported_devices)(const struct audio_hw_device *dev);
  ...
};
typedef struct audio_hw_device audio_hw_device_t;struct audio_module HAL_MODULE_INFO_SYM = {
    .common = {
        .tag = HARDWARE_MODULE_TAG,
        .module_api_version = AUDIO_MODULE_API_VERSION_0_1,
        .hal_api_version = HARDWARE_HAL_API_VERSION,
        .id = AUDIO_HARDWARE_MODULE_ID,
        .name = "NVIDIA Tegra Audio HAL",
        .author = "The Android Open Source Project",
        .methods = &hal_module_methods,
    },
};
