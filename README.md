    int redLed = D6;
    int greenLed = D5;
    int blueLed = D4;

    bool redOn = false;
    bool greenOn = false;
    bool blueOn = false;

    void setup() {
        pinMode(redLed, OUTPUT);
        pinMode(greenLed, OUTPUT);
        pinMode(blueLed, OUTPUT);
    
        Particle.function("led", toggleLed);

        digitalWrite(redLed, LOW);
        digitalWrite(greenLed, LOW);
        digitalWrite(blueLed, LOW);
    }

    int toggleLed(String command){
        if(command == "red"){
            if (redOn == true){
                digitalWrite(redLed, LOW);
                redOn = false;
            }
            else{
                digitalWrite(redLed, HIGH);
                redOn = true;
            }
        }
        if(command == "green"){
            if (greenOn == true){
                digitalWrite(greenLed, LOW);
                greenOn = false;
            }
            else{
                digitalWrite(greenLed, HIGH);
                greenOn = true;

            }
        }
        if(command == "blue"){
            if (blueOn == true){
                digitalWrite(blueLed, LOW);
                blueOn = false;
            }
            else{
                digitalWrite(blueLed, HIGH);
                blueOn = true;
            }
        }
    }

    void loop() {
    }
