# ControllerMonitorInfo
The data in this repository was put together for an experiment https://youtu.be/yLcukmRfVt8.

The `user_friendly_name`, `manufacturer_name`, and `product_code_id` of **monitors** and `product_string`, `manufacturer_string`, `vendor_id`, `product_id`, and `version_number` of **USB HID devices** were read from the user's PC during the experiment. Those values don't always make it obvious what the real world product name of the device is. These lists are a result of long tedious work (mostly on monitors) of trying to figure out the real product name. *This does not always work.* Some non-identical monitors will use the exact same `user_friendly_name`, `manufacturer_name`, and `product_code_id`. Other times, I was just not able to figure it out.

Sources used for identification:
* USB HIDs:
    * https://www.the-sz.com/products/usbid/
    * Checking the values for all the controllers I own (13 devices or 28 different scenarios when considering all the connection methods)
    * Steam controller database https://support.steampowered.com/kb_article.php?ref=5199-TOKV-4426&l=english
* Monitors:
    * https://github.com/linuxhw/EDID
    * Drivers directly from manufacturers homepages as well as several sites storing drivers and driver information
    * Crossreferencing such information with https://www.displayspecifications.com/en, amazon.com, and other shops

## Warning
I cannot guarantee the correctness of any of the listings. Use at your own risk and do not use it in any situation where correctness is critical. The purpose of publishing is to allow people to check the data for mistakes, look up input lag information, as well as for people trying to find a starting point of figuring out their monitor and controller based on the IDs. Many monitor names may be over- or underspecified because of product sub-versions that might or might not have differing IDs.

## Input lag
Source of the controller input lag numbers are my own measurements: https://inputlag.rocketscience.fyi. Input may vary between buttons, the csv only reports the average.

Sources of the monitor input lag numbers are always listed in the csv. Differing methods will give different lag results. The [Leo Bodnar lag tester](http://www.leobodnar.com/shop/index.php?main_page=product_info&cPath=89&products_id=212&zenid=185a6d1376b192e407c9b83975eb697f) only works with a 60 Hz signal and results are reported based on the center measurement. [RTINGS' testing](https://www.rtings.com/company/input-lag-tool) works similarly but the method generalizes to any refresh rate and VRR support. So does [Hardware Unboxed](https://youtu.be/081ccrxYwDo) but they only report VRR lag. Their numbers are closer to RTINGS non-VRR numbers which may be related to [RTINGS measuring VRR at 55fps](https://www.rtings.com/monitor/discussions/ZR_9nJVAnwGid7IN/which-input-lag-rating-matters-most-for-emulated-console-gaming-via-a-pc). Based on the VRR technology this shouldn't matter, but it may, if a monitor doesn't instantly scan out at lower refresh rates. Many monitors also do not show any higher VRR input lag on RTINGS. [SMTT 2.0](https://www.tftcentral.co.uk/articles/input_lag.htm) works at any refreshrate (no VRR) and is used by tftcentral.co.uk and pcmonitors.info, however, neither should be compared 1 to 1 to the other methods as it works differently. TFT central also subtracts the pixel response time from the measurement while pcmonitors doesn't.

### CSV format
.csv files are semicolon separated because the fields contain commas, such as `Nintendo Co., Ltd.`.

