# PlatformIo-Shortcuts

monitor_flags = --raw

monitor_speed = 115200

ESP32 One
CONFIG_BLINK_GPIO=21
SOLDERED BUTTON INPUT = GPIO23


INPUT FROM KEYBOARD
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
