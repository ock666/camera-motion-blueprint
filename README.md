## **Camera Motion Blueprint**
forked from https://github.com/apollo1220/blueprints

This blueprint allows you to capture timestamped snapshots from a camera in your home assistant, attach that snapshot to a notification, there is a person feature which will block the automation when the assigned person is home.

The only setup required for this blueprint to work is to make sure you have a directory created in the /config/www folder to match what you set within the blueprint.

It's not required but strongly recommended to have an additional automation in place to take care of cleaning up old files which will eventually accumulate over time. This can be accomplished by adding the following to your configuration.yaml file.

    shell_command:
      erase_images: find /config/www/%YOUR_DIRECTORY_NAME% -mtime +7 -exec rm -fr {} +

with the example above, 7 being the age in days of files to delete, upon restarting home assistant a new service will appear called:

    shell_command.erase_images
    
you can use this in a time based automation to periodically clean up old images
