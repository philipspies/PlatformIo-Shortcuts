# PlatformIo-Shortcuts

---------------------------------------
platformio.ini
---------------------------------------
monitor_flags = --raw
monitor_speed = 115200

---------------------------------------
GPIO's
---------------------------------------
ESP32 One
CONFIG_BLINK_GPIO=21
SOLDERED BUTTON INPUT = GPIO23

---------------------------------------
INPUT FROM KEYBOARD
---------------------------------------
#include <stdio.h>
#include <string.h>
    char c = 0;
    char str[100];
    memset(str, 0, sizeof(str));
    while (c != '\n')
    {
        c = getchar();
        if(c != 0xff)
        {
            str[(strlen(str))] = c;
            printf("%c", c);
        }
        vTaskDelay(10 / portTICK_PERIOD_MS);
    }
    
---------------------------------------
BLINK
---------------------------------------
    #define BLINK_GPIO 21
    gpio_pad_select_gpio(BLINK_GPIO);
    gpio_set_direction(BLINK_GPIO, GPIO_MODE_OUTPUT);
    while(1) {
	printf("Turning off the LED\n");
        gpio_set_level(BLINK_GPIO, 0);
        vTaskDelay(1000 / portTICK_PERIOD_MS);
	printf("Turning on the LED\n");
        gpio_set_level(BLINK_GPIO, 1);
        vTaskDelay(1000 / portTICK_PERIOD_MS);
    }
    
---------------------------------------

---------------------------------------
    
