# Imunify Security WordPress Plugin

## Overview

The **Imunify Security WordPress plugin** is designed exclusively for Imunify360 users, providing WordPress administrators with a comprehensive overview of malware that has been cleaned from their site. It integrates seamlessly with the Imunify360 platform to enhance your website's security.

## Prerequisites

* **WordPress Version**: 5.0.0 or higher
* **PHP Version**: 5.6 or higher
* **Imunify360**: 8.2.0 or higher

## Installation

Currently the plugin is not available in the WordPress plugin repository. You can install it manually by following the steps below:

1. Navigate to Imunify360 settings in the cPanel
2. Scroll down to the `WordPress Plugin` section
3. Tick the `Install WordPress plugin` checkbox and click the `Save changes` button
4. Plugin will be installed in the background to all WordPress installations on the server

![](/images/wordpress-plugin/panel-settings.png)

## Features

### Dashboard Widget

Plugin adds a dashboard widget that helps administrators keep track of their site's real-time security status including:

- the timestamps for the last and next scheduled scans
- detailed list of malware items that have been detected and cleaned, including the file path, signature, and the clean-up time

## Screenshots

### Admin widget - malware cleaned

![](/images/wordpress-plugin/widget-malware-cleaned.png)

### Malware details

![](/images/wordpress-plugin/malware-found-details.png)

### Admin widget - no malware found

![](/images/wordpress-plugin/widget-no-malware.png)

### Admin widget - site not protected
![](/images/wordpress-plugin/widget-not-protected.png)
