all: build deploy clean

build:
	avr-g++ main.cpp -o main.out -std=c++11 -mmcu=atmega328p -Wall -Wextra -O3
	avr-objcopy -j .text -j .data -O ihex main.out main.hex
	rm -rf main.out 

deploy:
	avrdude -c arduino -b 57600 -P /dev/ttyUSB0 -p atmega328p -vv -U flash:w:main.hex 

clean:
	rm -rf main.out
	rm -rf main.hex