# Duo: Programming Reference
---

The Duo is installed the customed Particle firmware by default during manufacturing. You can build your own applications around the system firmware, which with lots of functions and libraries built-in so that you can invoke them directly in your sketch. The programming language and application architecture are almost Arduino compatible -- all you want should be achieved in the `setup()` and `loop()` function.

* `setup()` - Runs once at the beginning of your program    
* `loop()` - Runs continuously over and over

E.g.:

    int led1 = D0; // Instead of writing D0 over and over again, we'll write led1

    /* The setup function is a standard part of any microcontroller program.
       It runs only once when the device boots up or is reset. */

    void setup() {
        pinMode(led1, OUTPUT);
    }

    /* Next we have the loop function, the other essential part of a microcontroller program. This routine gets
       repeated over and over, as quickly as possible and as many times as possible, after the setup function is called.

       Note: Code that blocks for too long (like more than 5 seconds), can make weird things happen 
       (like dropping the network connection). The built-in delay() function shown below safely interleaves required 
       background activity, so arbitrarily long delays can safely be done if you need them. */

    void loop() {  
        digitalWrite(led1, HIGH);  // To blink the LED, first we'll turn it on...
        delay(1000);               // We'll leave it on for 1 second...
        digitalWrite(led1, LOW);   // Then we'll turn it off...
        delay(1000);               // Wait 1 second...
        // And repeat!
    }


## Language Syntax

- [Structure](https://docs.particle.io/reference/firmware/photon/#structure)
- [Control Structures](https://docs.particle.io/reference/firmware/photon/#control-structures)
- [Further syntax](https://docs.particle.io/reference/firmware/photon/#further-syntax)
- [Arithmetic operators](https://docs.particle.io/reference/firmware/photon/#arithmetic-operators)
- [Boolean operators](https://docs.particle.io/reference/firmware/photon/#boolean-operators)
- [Bitwise operators](https://docs.particle.io/reference/firmware/photon/#bitwise-operators)
- [Compound operators](https://docs.particle.io/reference/firmware/photon/#compound-operators)
- [Variables](https://docs.particle.io/reference/firmware/photon/#variables)
- [Data Types](https://docs.particle.io/reference/firmware/photon/#data-types)


## Reference

Since the Duo shares most of the firmware source code with Particle Photon, most of the functions and libraries designed for Photon are valid for the Duo as well. Each of these functions and libraries is described extremely in detail on the [Particle Reference](https://docs.particle.io/reference/) website, so we're not going to duplicate it here, but only list the APIs for quick reference. Regarding to the reference on the unique features of the Duo, we will document it here in detail.

### Summary

##### Inherit from Particle Reference
- [Input/Output](#inputoutput)
- [Low Level Input/Output](#low-level-inputoutput)
- [Advanced I/O](#advanced-io)
- [Interrupts](#interrupts)
- [Software Timers](#software-timers)
- [Serial](#serial)
- [SPI](#spi)
- [Wire (I2C)](#wire-i2c)
- [CAN (CANbus)](#can-canbus)
- [Servo](#servo)
- [RGB](#rgb)
- [EEPROM Emulation](#eeprom-emulation)
- [Backup RAM (SRAM)](#backup-ram-sram)
- [Application Watchdog](#application-watchdog)
- [Time](#time)
- [Math](#math)
- [Random Numbers](#random-numbers)
- [String](#string)
- [WiFi](#wifi)
- [IPAddress](#ipaddress)
- [TCPServer](#tcpserver)
- [TCPClient](#tcpclient)
- [UDP](#udp)
- [Stream](#stream)
- [SoftAP HTTP Pages](#softap-http-pages)
- [Cloud Functions](#cloud-functions)
- [System Calls](#system-calls)
- [System Modes](#system-modes)
- [System Thread](#system-thread)
- [System Events](#system-events)
- [Macros](#macros)
- [Other Functions](#other-functions)
- [Preprocessor](https://docs.particle.io/reference/firmware/photon/#preprocessor)

##### Addition Reference

- [External SPI Flash](#external-spi-flash)
- [Bluetooth Low Energy](#bluetooth-low-energy)

---

### <span id="inputoutput">[Input/Output](https://docs.particle.io/reference/firmware/photon/#input-output)</span>

Built-in global function.        
[`pinMode()`](https://docs.particle.io/reference/firmware/photon/#pinmode-) - `INPUT`, `INPUT_PULLUP`, `INPUT_PULLDOWN` or `OUTPUT`    
[`getPinMode()`](https://docs.particle.io/reference/firmware/photon/#getpinmode-pin-)    
[`digitalWrite()`](https://docs.particle.io/reference/firmware/photon/#digitalwrite-) - `HIGH` or `LOW`    
[`digitalRead()`](https://docs.particle.io/reference/firmware/photon/#digitalread-)    
[`analogWrite()`](https://docs.particle.io/reference/firmware/photon/#analogwrite-pwm-) - PWM (0 ~ 255)    
[`analogWrite()`](https://docs.particle.io/reference/firmware/photon/#analog-output-dac-) - DAC (0 ~ 4095)    
[`analogRead()`](https://docs.particle.io/reference/firmware/photon/#analogread-adc-) - (0 ~ 4095)    
[`setADCSampleTime()`](https://docs.particle.io/reference/firmware/photon/#setadcsampletime-)

### <span id="low-level-inputoutput">[Low Level Input/Output](https://docs.particle.io/reference/firmware/photon/#low-level-input-output)</span>

Built-in global function.       
[`pinSetFast()`](https://docs.particle.io/reference/firmware/photon/#pinsetfast-)    
[`pinResetFast()`](https://docs.particle.io/reference/firmware/photon/#pinresetfast-)    
[`digitalWriteFast()`](https://docs.particle.io/reference/firmware/photon/#digitalwritefast-)     
[`pinReadFast()`](https://docs.particle.io/reference/firmware/photon/#pinreadfast-)   

### <span id="advanced-io">[Advanced I/O](https://docs.particle.io/reference/firmware/photon/#advanced-i-o)</span> 

Built-in global function.       
[`tone()`](https://docs.particle.io/reference/firmware/photon/#tone-)    
[`noTone()`](https://docs.particle.io/reference/firmware/photon/#notone-)    
[`shiftOut()`](https://docs.particle.io/reference/firmware/photon/#shiftout-)    
[`shiftIn()`](https://docs.particle.io/reference/firmware/photon/#shiftin-)          
[`pulseIn()`](https://docs.particle.io/reference/firmware/photon/#pulsein-)         
 
### <span id="interrupts">[Interrupts](https://docs.particle.io/reference/firmware/photon/#interrupts)</span>

Built-in global function.     
[`attachInterrupt()`](https://docs.particle.io/reference/firmware/photon/#attachinterrupt-)    
[`detachInterrupt()`](https://docs.particle.io/reference/firmware/photon/#detachinterrupt-)    
[`interrupts()`](https://docs.particle.io/reference/firmware/photon/#interrupts-)    
[`noInterrupts()`](https://docs.particle.io/reference/firmware/photon/#nointerrupts-)    

### <span id="software-timers">[Software Timers](https://docs.particle.io/reference/firmware/photon/#software-timers)</span>

Built-in class.      
constructor [`Timer`](https://docs.particle.io/reference/firmware/photon/#software-timers)    
[Class member callbacks](https://docs.particle.io/reference/firmware/photon/#class-member-callbacks)    
[`start()`](https://docs.particle.io/reference/firmware/photon/#start-)    
[`stop()`](https://docs.particle.io/reference/firmware/photon/#stop--2)    
[`changePeriod()`](https://docs.particle.io/reference/firmware/photon/#changeperiod-)    
[`reset()`](https://docs.particle.io/reference/firmware/photon/#reset--1)    
[`startFromISR()`](https://docs.particle.io/reference/firmware/photon/#startfromisr-)    
[`stopFromISR()`](https://docs.particle.io/reference/firmware/photon/#stopfromisr-)    
[`resetFromISR()`](https://docs.particle.io/reference/firmware/photon/#resetfromisr-)    
[`changePeriodFromISR()`](https://docs.particle.io/reference/firmware/photon/#changeperiodfromisr-)    
[`dispose()`](https://docs.particle.io/reference/firmware/photon/#dispose-)    
[`isActive()`](https://docs.particle.io/reference/firmware/photon/#isactive-)   

### <span id="serial">[Serial](https://docs.particle.io/reference/firmware/photon/#serial)</span>

Built-in instance `Serial`, `Serial1`, `Serial2`.    
    
Differing from the Photon, the USART2 is layed out to the side pins and the `Serial2` object is constructed in the system firmware, so that you can directly call the methods of `Serial2` without including extra header files.

[`begin()`](https://docs.particle.io/reference/firmware/photon/#begin-)    
[`end()`](https://docs.particle.io/reference/firmware/photon/#end-)    
[`available()`](https://docs.particle.io/reference/firmware/photon/#available-)    
[`availableForWrite()`](https://docs.particle.io/reference/firmware/photon/#availableforwrite-)    
[`blockOnOverrun()`](https://docs.particle.io/reference/firmware/photon/#blockonoverrun-)    
[`serialEvent()`](https://docs.particle.io/reference/firmware/photon/#serialevent-)    
[`peek()`](https://docs.particle.io/reference/firmware/photon/#peek-)    
[`write()`](https://docs.particle.io/reference/firmware/photon/#write-)    
[`read()`](https://docs.particle.io/reference/firmware/photon/#read-)    
[`print()`](https://docs.particle.io/reference/firmware/photon/#print-)    
[`println()`](https://docs.particle.io/reference/firmware/photon/#println-)    
[`printf()`](https://docs.particle.io/reference/firmware/photon/#printf-)    
[`printlnf()`](https://docs.particle.io/reference/firmware/photon/#printlnf-)    
[`flush()`](https://docs.particle.io/reference/firmware/photon/#flush-)    
[`halfduplex()`](https://docs.particle.io/reference/firmware/photon/#halfduplex-)    
Inherited [Stream](#stream) methods 

### <span id="spi">[SPI](https://docs.particle.io/reference/firmware/photon/#spi)</span>

Built-in instance `SPI`, `SPI1`.    
[`begin()`](https://docs.particle.io/reference/firmware/photon/#begin--1)    
[`end()`](https://docs.particle.io/reference/firmware/photon/#end--1)    
[`setBitOrder()`](https://docs.particle.io/reference/firmware/photon/#setbitorder-)    
[`setClockSpeed()`](https://docs.particle.io/reference/firmware/photon/#setclockspeed)    
[`setClickDividerReference()`](https://docs.particle.io/reference/firmware/photon/#setclockdividerreference)    
[`setClockDivider()`](https://docs.particle.io/reference/firmware/photon/#setclockdivider-)    
[`setDataMode()`](https://docs.particle.io/reference/firmware/photon/#setdatamode-)    
[`transfer()`](https://docs.particle.io/reference/firmware/photon/#transfer-)    
[`transferCancel()`](https://docs.particle.io/reference/firmware/photon/#transfercancel-)    
[`onSelect()`](https://docs.particle.io/reference/firmware/photon/#onselect-)    
[`available()`](https://docs.particle.io/reference/firmware/photon/#available--1)    

### <span id="wire-i2c">[Wire (I2C)](https://docs.particle.io/reference/firmware/photon/#wire-i2c-)</span>

Built-in instance `I2C`.     
[`setSpeed()`](https://docs.particle.io/reference/firmware/photon/#setspeed-)    
[`stretchClock()`](https://docs.particle.io/reference/firmware/photon/#stretchclock-)    
[`begin()`](https://docs.particle.io/reference/firmware/photon/#begin--2)    
[`end()`](https://docs.particle.io/reference/firmware/photon/#end--2)    
[`isEnabled()`](https://docs.particle.io/reference/firmware/photon/#isenabled-)    
[`requestFrom()`](https://docs.particle.io/reference/firmware/photon/#requestfrom-)    
[`reset()`](https://docs.particle.io/reference/firmware/photon/#reset-)    
[`beginTransmission()`](https://docs.particle.io/reference/firmware/photon/#begintransmission-)    
[`endTransmission()`](https://docs.particle.io/reference/firmware/photon/#endtransmission-)    
[`write()`](https://docs.particle.io/reference/firmware/photon/#write--1)    
[`available()`](https://docs.particle.io/reference/firmware/photon/#available--2)    
[`read()`](https://docs.particle.io/reference/firmware/photon/#read--1)    
[`peek()`](https://docs.particle.io/reference/firmware/photon/#peek--1)    
[`onReceive()`](https://docs.particle.io/reference/firmware/photon/#onreceive-)    
[`onRequest()`](https://docs.particle.io/reference/firmware/photon/#onrequest-)    
Inherited [Stream](#stream) methods  

### <span id="can-canbus">[CAN (CANbus)](https://docs.particle.io/reference/firmware/photon/#can-canbus-)</span>

Built-in class.    
constructor [`CANChannel()`](https://docs.particle.io/reference/firmware/photon/#canchannel)    
[`CANMessage`](https://docs.particle.io/reference/firmware/photon/#canmessage)    
[`begin()`](https://docs.particle.io/reference/firmware/photon/#begin--3)    
[`end()`](https://docs.particle.io/reference/firmware/photon/#end--3)     
[`available()`](https://docs.particle.io/reference/firmware/photon/#available--3)    
[`receive()`](https://docs.particle.io/reference/firmware/photon/#receive-)    
[`transmit()`](https://docs.particle.io/reference/firmware/photon/#transmit-)    
[`addFilter()`](https://docs.particle.io/reference/firmware/photon/#addfilter-)    
[`clearFilters()`](https://docs.particle.io/reference/firmware/photon/#clearfilters-)    
[`isEnabled()`](https://docs.particle.io/reference/firmware/photon/#isenabled--1)    
[`errorStatus()`](https://docs.particle.io/reference/firmware/photon/#errorstatus-)    

### <span id="servo">[Servo](https://docs.particle.io/reference/firmware/photon/#servo)</span>

Built-in class.     
constructor [`Servo()`](https://docs.particle.io/reference/firmware/photon/#servo)    
[`attach()`](https://docs.particle.io/reference/firmware/photon/#attach-)     
[`attached()`](https://docs.particle.io/reference/firmware/photon/#attached-)    
[`detach()`](https://docs.particle.io/reference/firmware/photon/#detach-)           
[`write()`](https://docs.particle.io/reference/firmware/photon/#write--5)    
[`writeMicroseconds()`](https://docs.particle.io/reference/firmware/photon/#writemicroseconds-)    
[`read()`](https://docs.particle.io/reference/firmware/photon/#read--4)          
[`setTrim()`](https://docs.particle.io/reference/firmware/photon/#settrim-)    

### <span id="rgb">[RGB](https://docs.particle.io/reference/firmware/photon/#rgb)</span>

Built-in instance `RGB`.    
[`control()`](https://docs.particle.io/reference/firmware/photon/#control-user_control-)    
[`controlled()`](https://docs.particle.io/reference/firmware/photon/#controlled-)    
[`color()`](https://docs.particle.io/reference/firmware/photon/#color-red-green-blue-)    
[`brightness()`](https://docs.particle.io/reference/firmware/photon/#brightness-val-)    
[`onChange()`](https://docs.particle.io/reference/firmware/photon/#onchange-handler-)    

### <span id="eeprom-emulation">[EEPROM Emulation](https://docs.particle.io/reference/firmware/photon/#eeprom)</span>

Built-in instance `EEPROM`.    
[`length()`](https://docs.particle.io/reference/firmware/photon/#length-)    
[`put()`](https://docs.particle.io/reference/firmware/photon/#put-)    
[`get()`](https://docs.particle.io/reference/firmware/photon/#get-)    
[`read()`](https://docs.particle.io/reference/firmware/photon/#read--5)    
[`write()`](https://docs.particle.io/reference/firmware/photon/#write--6)    
[`clear()`](https://docs.particle.io/reference/firmware/photon/#clear-)    
[`hasPendingErase()`](https://docs.particle.io/reference/firmware/photon/#haspendingerase-)    
[`performPendingErase()`](https://docs.particle.io/reference/firmware/photon/#performpendingerase-)    

### <span id="backup-ram-sram">[Backup RAM (SRAM)](https://docs.particle.io/reference/firmware/photon/#backup-ram-sram-)</span>

[Storing data in Backup RAM (SRAM)](https://docs.particle.io/reference/firmware/photon/#storing-data-in-backup-ram-sram-)    
[Enabling Backup RAM (SRAM)](https://docs.particle.io/reference/firmware/photon/#enabling-backup-ram-sram-)    
[Making changes to the layout or bytes of retained variables](https://docs.particle.io/reference/firmware/photon/#making-changes-to-the-layout-or-types-of-retained-variables)    

### <span id="application-watchdog">[Application Watchdog](https://docs.particle.io/reference/firmware/photon/#application-watchdog)</span>

Built-in class.    
constructor [`ApplicationWatchdog()`](https://docs.particle.io/reference/firmware/photon/#application-watchdog)    
[`checkin()`](https://docs.particle.io/reference/firmware/photon/#application-watchdog)    

### <span id="time">[Time](https://docs.particle.io/reference/firmware/photon/#time)</span>

Built-in instance `Time`.    
[`hour()`](https://docs.particle.io/reference/firmware/photon/#hour-)    
[`hourFormat12()`](https://docs.particle.io/reference/firmware/photon/#hourformat12-)    
[`isAM()`](https://docs.particle.io/reference/firmware/photon/#isam-)    
[`isPM()`](https://docs.particle.io/reference/firmware/photon/#ispm-)    
[`minute()`](https://docs.particle.io/reference/firmware/photon/#minute-)    
[`second()`](https://docs.particle.io/reference/firmware/photon/#second-)    
[`day()`](https://docs.particle.io/reference/firmware/photon/#day-)        
[`weekday()`](https://docs.particle.io/reference/firmware/photon/#weekday-)
[`month()`](https://docs.particle.io/reference/firmware/photon/#month-)    
[`year()`](https://docs.particle.io/reference/firmware/photon/#year-)    
[`now()`](https://docs.particle.io/reference/firmware/photon/#now-)    
[`local()`](https://docs.particle.io/reference/firmware/photon/#local-)    
[`zone()`](https://docs.particle.io/reference/firmware/photon/#zone-)    
[`setTime()`](https://docs.particle.io/reference/firmware/photon/#settime-)    
[`timeStr()`](https://docs.particle.io/reference/firmware/photon/#timestr-)    
[`format()`](https://docs.particle.io/reference/firmware/photon/#format-)    
[`setFormat()`](https://docs.particle.io/reference/firmware/photon/#setformat-)    
[`getFormat()`](https://docs.particle.io/reference/firmware/photon/#getformat-)    
[`millis()`](https://docs.particle.io/reference/firmware/photon/#millis-)    
[`micros()`](https://docs.particle.io/reference/firmware/photon/#micros-)    
[`delay()`](https://docs.particle.io/reference/firmware/photon/#delay-)    
[`delayMicroseconds()`](https://docs.particle.io/reference/firmware/photon/#delaymicroseconds-)    

### <span id="math">[Math](https://docs.particle.io/reference/firmware/photon/#math)</span>

Built-in global function.    
[`min()`](https://docs.particle.io/reference/firmware/photon/#min-)    
[`max()`](https://docs.particle.io/reference/firmware/photon/#max-)    
[`abs()`](https://docs.particle.io/reference/firmware/photon/#abs-)    
[`constrain()`](https://docs.particle.io/reference/firmware/photon/#constrain-)    
[`map()`](https://docs.particle.io/reference/firmware/photon/#map-)    
[`pow()`](https://docs.particle.io/reference/firmware/photon/#pow-)    
[`sqrt()`](https://docs.particle.io/reference/firmware/photon/#sqrt-)    

### <span id="random-numbers">[Random Numbers](https://docs.particle.io/reference/firmware/photon/#random-numbers)</span>

Built-in global function.    
[`random()`](https://docs.particle.io/reference/firmware/photon/#random-)    
[`randomSeed()`](https://docs.particle.io/reference/firmware/photon/#randomseed-)    

### <span id="string">[String](https://docs.particle.io/reference/firmware/photon/#string-class)</span>

Built-in class.    
constructor [`String()`](https://docs.particle.io/reference/firmware/photon/#string-)    
[`charAt()`](https://docs.particle.io/reference/firmware/photon/#charat-)    
[`compareTo()`](https://docs.particle.io/reference/firmware/photon/#compareto-)    
[`concat()`](https://docs.particle.io/reference/firmware/photon/#concat-)    
[`endsWith()`](https://docs.particle.io/reference/firmware/photon/#endswith-)    
[`startsWith()`](https://docs.particle.io/reference/firmware/photon/#startswith-)    
[`equals()`](https://docs.particle.io/reference/firmware/photon/#equals-)    
[`equalsIgnoreCase()`](https://docs.particle.io/reference/firmware/photon/#equalsignorecase-)    
[`format()`](https://docs.particle.io/reference/firmware/photon/#format--1)    
[`getBytes()`](https://docs.particle.io/reference/firmware/photon/#getbytes-)    
[`indexOf()`](https://docs.particle.io/reference/firmware/photon/#indexof-)    
[`lastIndexOf()`](https://docs.particle.io/reference/firmware/photon/#lastindexof-)    
[`length()`](https://docs.particle.io/reference/firmware/photon/#length--1)    
[`remove()`](https://docs.particle.io/reference/firmware/photon/#remove-)    
[`replace()`](https://docs.particle.io/reference/firmware/photon/#replace-)    
[`reserve()`](https://docs.particle.io/reference/firmware/photon/#reserve-)    
[`setCharAt()`](https://docs.particle.io/reference/firmware/photon/#setcharat-)    
[`substring()`](https://docs.particle.io/reference/firmware/photon/#substring-)    
[`toCharArray()`](https://docs.particle.io/reference/firmware/photon/#tochararray-)    
[`toFloat()`](https://docs.particle.io/reference/firmware/photon/#tofloat-)    
[`toInt()`](https://docs.particle.io/reference/firmware/photon/#toint-)    
[`toLowerCase()`](https://docs.particle.io/reference/firmware/photon/#tolowercase-)    
[`toUpperCase()`](https://docs.particle.io/reference/firmware/photon/#touppercase-)    
[`trim()`](https://docs.particle.io/reference/firmware/photon/#trim-)    

### <span id="wifi">[WiFi](https://docs.particle.io/reference/firmware/photon/#wifi)</span>

Built-in instance `WiFi`.    
[`on()`](https://docs.particle.io/reference/firmware/photon/#on-)    
[`off()`](https://docs.particle.io/reference/firmware/photon/#off-)    
[`connect()`](https://docs.particle.io/reference/firmware/photon/#connect-)    
[`disconnect()`](https://docs.particle.io/reference/firmware/photon/#disconnect-)    
[`connecting()`](https://docs.particle.io/reference/firmware/photon/#connecting-)    
[`ready()`](https://docs.particle.io/reference/firmware/photon/#ready-)    
[`selectAntenna()`](https://docs.particle.io/reference/firmware/photon/#selectantenna-)    
[`listen()`](https://docs.particle.io/reference/firmware/photon/#listen-)    
[`listening()`](https://docs.particle.io/reference/firmware/photon/#listening-)    
[`setCredentials()`](https://docs.particle.io/reference/firmware/photon/#setcredentials-)    
[`getCredentials()`](https://docs.particle.io/reference/firmware/photon/#getcredentials-)    
[`clearCredentials()`](https://docs.particle.io/reference/firmware/photon/#clearcredentials-)    
[`hasCredentials()`](https://docs.particle.io/reference/firmware/photon/#hascredentials-)    
[`macAddress()`](https://docs.particle.io/reference/firmware/photon/#macaddress-)    
[`SSID()`](https://docs.particle.io/reference/firmware/photon/#ssid-)    
[`BSSID()`](https://docs.particle.io/reference/firmware/photon/#bssid-)    
[`RSSI()`](https://docs.particle.io/reference/firmware/photon/#rssi-)    
[`ping()`](https://docs.particle.io/reference/firmware/photon/#ping-)    
[`scan()`](https://docs.particle.io/reference/firmware/photon/#scan-)    
[`resolve()`](https://docs.particle.io/reference/firmware/photon/#resolve-)        
[`localIP()`](https://docs.particle.io/reference/firmware/photon/#localip-)
[`subnetMask()`](https://docs.particle.io/reference/firmware/photon/#subnetmask-)    
[`gatewayIP()`](https://docs.particle.io/reference/firmware/photon/#gatewayip-)    
[`dnsServerIP()`](https://docs.particle.io/reference/firmware/photon/#dnsserverip-)    
[`dhcpServerIP()`](https://docs.particle.io/reference/firmware/photon/#dhcpserverip-)    
[`setStaticIP()`](https://docs.particle.io/reference/firmware/photon/#setstaticip-)    
[`useStaticIP()`](https://docs.particle.io/reference/firmware/photon/#usestaticip-)    
[`useDynamicIP()`](https://docs.particle.io/reference/firmware/photon/#usedynamicip-)    

### <span id="ipaddress">[IPAddress](https://docs.particle.io/reference/firmware/photon/#ipaddress)</span>

Built-in class.    
constructor [`IPAddress()`](https://docs.particle.io/reference/firmware/photon/#ipaddress)    
[`=`](https://docs.particle.io/reference/firmware/photon/#ipaddress)    
[`==`](https://docs.particle.io/reference/firmware/photon/#ipaddress)    
[`!=`](https://docs.particle.io/reference/firmware/photon/#ipaddress)    
[`[]`](https://docs.particle.io/reference/firmware/photon/#ipaddress)    

### <span id="tcpserver">[TCPServer](https://docs.particle.io/reference/firmware/photon/#tcpserver)</span>

Built-in class.    
constructor [`TCPServer()`](https://docs.particle.io/reference/firmware/photon/#tcpserver)    
[`begin()`](https://docs.particle.io/reference/firmware/photon/#begin--4)    
[`available()`](https://docs.particle.io/reference/firmware/photon/#available--4)    
[`write()`](https://docs.particle.io/reference/firmware/photon/#write--2)    
[`print()`](https://docs.particle.io/reference/firmware/photon/#print--1)    
[`println()`](https://docs.particle.io/reference/firmware/photon/#println--1)    

### <span id="tcpclient">[TCPClient](https://docs.particle.io/reference/firmware/photon/#tcpclient)</span>

Built-in class.    
constructor [`TCPClient()`](https://docs.particle.io/reference/firmware/photon/#tcpclient)    
[`connect()`](https://docs.particle.io/reference/firmware/photon/#connect--1)    
[`connected()`](https://docs.particle.io/reference/firmware/photon/#connected-)    
[`stop()`](https://docs.particle.io/reference/firmware/photon/#stop-)     
[`write()`](https://docs.particle.io/reference/firmware/photon/#write--3)    
[`print()`](https://docs.particle.io/reference/firmware/photon/#print--2)    
[`println()`](https://docs.particle.io/reference/firmware/photon/#println--2)    
[`available()`](https://docs.particle.io/reference/firmware/photon/#available--5)    
[`read()`](https://docs.particle.io/reference/firmware/photon/#read--2)    
[`flush()`](https://docs.particle.io/reference/firmware/photon/#flush--1)    
[`remoteIP()`](https://docs.particle.io/reference/firmware/photon/#remoteip-)     
Inherited [Stream](#stream) methods   

### <span id="udp">[UDP](https://docs.particle.io/reference/firmware/photon/#udp)</span>

Built-in class.    
constructor [`UDP()`](https://docs.particle.io/reference/firmware/photon/#udp)    
[`begin()`](https://docs.particle.io/reference/firmware/photon/#begin--5)    
[`stop()`](https://docs.particle.io/reference/firmware/photon/#stop--1)     
[`available()`](https://docs.particle.io/reference/firmware/photon/#available--6)    
[`beginPacket()`](https://docs.particle.io/reference/firmware/photon/#beginpacket-)     
[`endPacket()`](https://docs.particle.io/reference/firmware/photon/#endpacket-)    
[`sendPacket()`](https://docs.particle.io/reference/firmware/photon/#sendpacket-)    
[`parsePacket()`](https://docs.particle.io/reference/firmware/photon/#parsepacket-)      
[`write()`](https://docs.particle.io/reference/firmware/photon/#write--4)      
[`read()`](https://docs.particle.io/reference/firmware/photon/#read--3)        
[`remoteIP()`](https://docs.particle.io/reference/firmware/photon/#remoteip--1)    
[`remotePort()`](https://docs.particle.io/reference/firmware/photon/#remoteport-)    
[`setBuffer()`](https://docs.particle.io/reference/firmware/photon/#setbuffer-)    
[`releaseBuffer()`](https://docs.particle.io/reference/firmware/photon/#releasebuffer-)        
[`joinMulticast()`](https://docs.particle.io/reference/firmware/photon/#joinmulticast-)    
[`leaveMulticast()`](https://docs.particle.io/reference/firmware/photon/#leavemulticast-)    
Inherited [Stream](#stream) methods 

### <span id="stream">[Stream](https://docs.particle.io/reference/firmware/photon/#stream-class)</span>

Built-in class, inherited by `Serial`, `Wire`, `TCPClient`, `UDP`.    
[`setTimeout()`](https://docs.particle.io/reference/firmware/photon/#settimeout-)    
[`find()`](https://docs.particle.io/reference/firmware/photon/#find-)    
[`findUntil()`](https://docs.particle.io/reference/firmware/photon/#finduntil-)    
[`readBytes()`](https://docs.particle.io/reference/firmware/photon/#readbytes-)    
[`readBytesUntil()`](https://docs.particle.io/reference/firmware/photon/#readbytesuntil-)    
[`readString()`](https://docs.particle.io/reference/firmware/photon/#readstring-)    
[`readStringUntil()`](https://docs.particle.io/reference/firmware/photon/#readstringuntil-)    
[`parseInt()`](https://docs.particle.io/reference/firmware/photon/#parseint-)    
[`parseFloat()`](https://docs.particle.io/reference/firmware/photon/#parsefloat-)    

### <span id="softap-http-pages">[SoftAP HTTP Pages](https://docs.particle.io/reference/firmware/photon/#softap-http-pages)</span>

[The page callback function](https://docs.particle.io/reference/firmware/photon/#the-page-callback-function)    
[Retrieving the request data](https://docs.particle.io/reference/firmware/photon/#retrieving-the-request-data)    
[Sending a response](https://docs.particle.io/reference/firmware/photon/#sending-a-response)    
[The default page](https://docs.particle.io/reference/firmware/photon/#the-default-page)    
[Sending a Redirect](https://docs.particle.io/reference/firmware/photon/#sending-a-redirect)    

### <span id="cloud-functions">[Cloud Functions](https://docs.particle.io/reference/firmware/photon/#cloud-functions)</span>

Built-in instance `Particle`.    
[`connect()`](https://docs.particle.io/reference/firmware/photon/#particle-connect-)    
[`connected()`](https://docs.particle.io/reference/firmware/photon/#particle-connected-)    
[`process()`](https://docs.particle.io/reference/firmware/photon/#particle-process-)    
[`disconnect()`](https://docs.particle.io/reference/firmware/photon/#particle-disconnect-)    
[`variable()`](https://docs.particle.io/reference/firmware/photon/#particle-variable-) - Expose a variable through the Cloud so that it can be called with **GET** method     
[`function()`](https://docs.particle.io/reference/firmware/photon/#particle-function-) - Expose a function through the Cloud so that it can be called with **POST** method     
[`publish()`](https://docs.particle.io/reference/firmware/photon/#particle-publish-) - Publish an event through the Particle Cloud that will be forwarded to all registered listeners    
[`subscribe()`](https://docs.particle.io/reference/firmware/photon/#particle-subscribe-) - Subscribe to events published by devices    
[`unsubscribe()`](https://docs.particle.io/reference/firmware/photon/#particle-unsubscribe-) - Removes all subscription handlers previously registered with `Particle.subscribe()`    
[`syncTime()`](https://docs.particle.io/reference/firmware/photon/#particle-synctime-)    
[Get Public IP](https://docs.particle.io/reference/firmware/photon/#get-public-ip)    
[Get Device name](https://docs.particle.io/reference/firmware/photon/#get-device-name)    
[Get Random seed](https://docs.particle.io/reference/firmware/photon/#get-random-seed)    

### <span id="system-calls">[System Calls](https://docs.particle.io/reference/firmware/photon/#system-calls)</span>

Built-in instance `System`.    
[`version()`](https://docs.particle.io/reference/firmware/photon/#version-)    
[`versionNumber()`](https://docs.particle.io/reference/firmware/photon/#versionnumber-)    
[`buttonPushed()`](https://docs.particle.io/reference/firmware/photon/#buttonpushed-)    
[`ticks()`](https://docs.particle.io/reference/firmware/photon/#system-cycle-counter)    
[`ticksPerMicrosecond()`](https://docs.particle.io/reference/firmware/photon/#system-cycle-counter)    
[`ticksDelay()`](https://docs.particle.io/reference/firmware/photon/#system-cycle-counter)    
[`freeMemory()`](https://docs.particle.io/reference/firmware/photon/#freememory-)    
[`dfu()`](https://docs.particle.io/reference/firmware/photon/#dfu-)    
[`deviceID()`](https://docs.particle.io/reference/firmware/photon/#deviceid-)    
[`enterSafeMode()`](https://docs.particle.io/reference/firmware/photon/#entersafemode-)    
[`sleep()`](https://docs.particle.io/reference/firmware/photon/#sleep-sleep-)    
[`reset()`](https://docs.particle.io/reference/firmware/photon/#reset--2)    
[`on()`](https://docs.particle.io/reference/firmware/photon/#system-events-overview) - register a system event handler    
[`enableUpdates()`](https://docs.particle.io/reference/firmware/photon/#system-enableupdates-)    
[`disableUpdates()`](https://docs.particle.io/reference/firmware/photon/#system-disableupdates-)     
[`updatesEnabled()`](https://docs.particle.io/reference/firmware/photon/#system-updatesenabled-)    
[`updatesPending()`](https://docs.particle.io/reference/firmware/photon/#system-updatespending-)    

### <span id="system-modes">[System Modes](https://docs.particle.io/reference/firmware/photon/#system-modes)</span>

[`SYSTEM_MODE()`](https://docs.particle.io/reference/firmware/photon/#system-modes) - default to `AUTOMATIC` mode        

- [`AUTOMATIC`](https://docs.particle.io/reference/firmware/photon/#automatic-mode): Automatically try to connect to Wi-Fi and the Particle Cloud and handle the cloud messages.    
- [`SEMI_AUTOMATIC`](https://docs.particle.io/reference/firmware/photon/#semi-automatic-mode): Manually connect to Wi-Fi and the Particle Cloud, but automatically handle the cloud messages.    
- [`MANUAL`](https://docs.particle.io/reference/firmware/photon/#manual-mode): Manually connect to Wi-Fi and the Particle Cloud and handle the cloud messages.

### <span id="system-thread">[System Thread](https://docs.particle.io/reference/firmware/photon/#system-thread)</span>

[`SYSTEM_THREAD()`](https://docs.particle.io/reference/firmware/photon/#system-thread)    
[`SINGLE_THREADED_BLOCK()`](https://docs.particle.io/reference/firmware/photon/#single_threaded_block-)    
[`AUTOMIC_BLOCK()`](https://docs.particle.io/reference/firmware/photon/#atomic_block-)    
[System Threading Behavior](https://docs.particle.io/reference/firmware/photon/#system-threading-behavior)    
[System Functions](https://docs.particle.io/reference/firmware/photon/#system-functions)    
[Task Switching](https://docs.particle.io/reference/firmware/photon/#task-switching)    
[Synchronizing Access to Shared System Resources](https://docs.particle.io/reference/firmware/photon/#synchronizing-access-to-shared-system-resources)    
[Waiting for the system](https://docs.particle.io/reference/firmware/photon/#waiting-for-the-system)    

### <span id="system-events">[System Events](https://docs.particle.io/reference/firmware/photon/#system-events)</span>

[System Events Overview](https://docs.particle.io/reference/firmware/photon/#system-events-overview)    
[System Events Reference](https://docs.particle.io/reference/firmware/photon/#system-events-reference)    

### <span id="macros">[Macros](https://docs.particle.io/reference/firmware/photon/#macros)</span>

[`STARTUP()`](https://docs.particle.io/reference/firmware/photon/#startup-)    
[`PRODUCT_ID()`](https://docs.particle.io/reference/firmware/photon/#product_id-)    

### <span id="other-functions">[Other Functions](https://docs.particle.io/reference/firmware/photon/#other-functions)</span>

Note that most of the functions in newlib described at [https://sourceware.org/newlib/libc.html](https://sourceware.org/newlib/libc.html) are available for use in addition to the functions outlined above.

### <span id="external-spi-flash">External SPI Flash</span> 



### <span id="bluetooth-low-energy">Bluetooth Low Energy</span> 




## Support

* [RedBear Discussion](http://discuss.redbear.cc)
* [Particle Community](https://community.particle.io)


## License

Copyright (c) 2016 Red Bear

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.