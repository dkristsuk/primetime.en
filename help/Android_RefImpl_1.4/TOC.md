---
cloud: experience-cloud
product: adobe
archtype: end-user
user-guide: null
---

# Table of Contents

+ [PSDK 1.4 for Android Reference Implementation](c_1.4_title-page/c_1.4_title-page.md)
    + [How to use the Primetime reference implementation](c_1.4_title-page/c_1.4_how-to-use-ref-player/c_1.4_how-to-use-ref-player.md)
        + [Reference implementation structure](c_1.4_title-page/c_1.4_how-to-use-ref-player/c_1.4_ref-player-structure.md)
        + [How to use feature managers](c_1.4_title-page/c_1.4_how-to-use-ref-player/c_1.4_using-feature-managers/c_1.4_using-feature-managers.md)
            + [Creating feature managers by passing configuration information to the MediaPlayer...](c_1.4_title-page/c_1.4_how-to-use-ref-player/c_1.4_using-feature-managers/c_1.4_creating-feature-managers.md)
            + [Turning features on or off using ManagerFactory](c_1.4_title-page/c_1.4_how-to-use-ref-player/c_1.4_using-feature-managers/c_1.4_turning-features-on-off.md)
            + [Handling events](c_1.4_title-page/c_1.4_how-to-use-ref-player/c_1.4_using-feature-managers/c_1.4_handling-events.md)
    + [Set up your development environment](c_1.4_title-page/t_1.4_set-up-dev-environment/t_1.4_set-up-dev-environment.md)
        + [Download and configure prerequisite software](c_1.4_title-page/t_1.4_set-up-dev-environment/t_1.4_download-prereqs-android.md)
        + [Build the Primetime reference implementation](c_1.4_title-page/t_1.4_set-up-dev-environment/t_1.4_install-the-ref-player-project.md)
        + [Explore the code](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_exploring-code.md)
            + [PlayerFragment](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_player-fragment.md)
            + [Feature managers](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_about-psdk-feature-managers.md)
            + [ConfigProvider](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_config-provider.md)
            + [SettingsActivity](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_settings-activity.md)
            + [Catalog format](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_catalog-format/c_1.4_catalog-format.md)
                + [JSON object for Primetime ads](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_catalog-format/r_1.4_json-pt-ads.md)
                + [JSON object for direct ad breaks](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_catalog-format/r_1.4_json-direct-ad-breaks.md)
                + [JSON object for custom ad markers](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_catalog-format/r_1.4_json-custom-ad-markers.md)
                + [JSON object for entitlement resource ID](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/c_1.4_catalog-format/r_1.4_json-entitlement-resource-id.md)
            + [Example JSON feed format](c_1.4_title-page/t_1.4_set-up-dev-environment/c_1.4_exploring-code/r_1.4_example-json-feed-format.md)
    + [Essential operations of video playback](c_1.4_title-page/c_1.4_video-playback/c_1.4_video-playback.md)
        + [Enable video playback](c_1.4_title-page/c_1.4_video-playback/t_1.4_enable-video-playback/t_1.4_enable-video-playback.md)
            + [Related API documentation](c_1.4_title-page/c_1.4_video-playback/t_1.4_enable-video-playback/r_1.4_api-hls-playback.md)
        + [DRM content protection](c_1.4_title-page/c_1.4_video-playback/c_1.4_content-protection/c_1.4_content-protection.md)
            + [Add content protection to the player](c_1.4_title-page/c_1.4_video-playback/c_1.4_content-protection/t_1.4_add-content-protection.md)
            + [Related API documentation](c_1.4_title-page/c_1.4_video-playback/c_1.4_content-protection/r_1.4_api-content-protection.md)
        + [Multiple bit rates](c_1.4_title-page/c_1.4_video-playback/c_1.4_mbr/c_1.4_mbr.md)
            + [Enabling custom ABR control in the reference implementation](c_1.4_title-page/c_1.4_video-playback/c_1.4_mbr/t_1.4_disable-abr.md)
            + [Configure for low bit rates](c_1.4_title-page/c_1.4_video-playback/c_1.4_mbr/t_1.4_configure-for-low-bit-rate.md)
        + [DVR](c_1.4_title-page/c_1.4_video-playback/c_1.4_dvr/c_1.4_dvr.md)
            + [DVR without ad insertion](c_1.4_title-page/c_1.4_video-playback/c_1.4_dvr/c_1.4_dvr-without-ad-insertion.md)
            + [DVR with ad insertion](c_1.4_title-page/c_1.4_video-playback/c_1.4_dvr/c_1.4_dvr-with-ad-insertion.md)
            + [Choosing a custom starting point for DVR](c_1.4_title-page/c_1.4_video-playback/c_1.4_dvr/t_1.4_dvr_custom-start-point.md)
            + [Set a custom start time in the reference implementation](c_1.4_title-page/c_1.4_video-playback/c_1.4_dvr/t_1.4_set-custom-start-time-dvr.md)
        + [Display QoS playback and device statistics](c_1.4_title-page/c_1.4_video-playback/t_1.4_qos-statistics/t_1.4_qos-statistics.md)
            + [Enable or disable QoS statistics reporting](c_1.4_title-page/c_1.4_video-playback/t_1.4_qos-statistics/t_1.4_qos-enable-disable.md)
            + [Related API documentation](c_1.4_title-page/c_1.4_video-playback/t_1.4_qos-statistics/r_1.4_api-qos.md)
    + [Ad insertion](c_1.4_title-page/c_1.4_ad-insertion/c_1.4_ad-insertion.md)
        + [Ad insertion types](c_1.4_title-page/c_1.4_ad-insertion/c_1.4_ad-insertion-types.md)
        + [Add advertising](c_1.4_title-page/c_1.4_ad-insertion/t_1.4_add-advertising.md)
        + [Related API documentation](c_1.4_title-page/c_1.4_ad-insertion/r_1.4_aps-callbacks-ad-insertion.md)
    + [Late-binding audio](c_1.4_title-page/c_1.4_late-binding-audio/c_1.4_late-binding-audio.md)
        + [Integrate late-binding audio](c_1.4_title-page/c_1.4_late-binding-audio/t_1.4_aa_enable.md)
        + [Select the audio tracks](c_1.4_title-page/c_1.4_late-binding-audio/t_1.4_select-audio-tracks.md)
        + [Related API documentation](c_1.4_title-page/c_1.4_late-binding-audio/r_1.4_aa-api-callbacks.md)
    + [Primetime authentication entitlement flows](c_1.4_title-page/c_1.4_paytvpass-entitlement/c_1.4_paytvpass-entitlement.md)
        + [Entitlement Manager Overview](c_1.4_title-page/c_1.4_paytvpass-entitlement/c_1.4_entitlement-overvivew.md)
        + [Integrate Primetime authentication](c_1.4_title-page/c_1.4_paytvpass-entitlement/t_1.4_integrate-pass.md)
        + [Configure Adobe Analytics Reporting](c_1.4_title-page/c_1.4_paytvpass-entitlement/t_1.4_pass-analytics-setup.md)
        + [Related API documentation](c_1.4_title-page/c_1.4_paytvpass-entitlement/r_1.4_pass-apis-callbacks.md)
    + [Video Analytics](c_1.4_title-page/c_1.4_video-analytics/c_1.4_video-analytics.md)
        + [Create the Video Analytics Manager](c_1.4_title-page/c_1.4_video-analytics/t_1.4_create-video-analytics-manager.md)
        + [Configure Video Analytics](c_1.4_title-page/c_1.4_video-analytics/t_1.4_configure-video-analytics-manager.md)
        + [Related API documentation](c_1.4_title-page/c_1.4_video-analytics/r_1.4_va-apis-callbacks.md)
    + [Build a custom user interface](c_1.4_title-page/t_1.4_build-custom-ui.md)
    + [Troubleshooting](c_1.4_title-page/c_1.4_troubleshooting.md)