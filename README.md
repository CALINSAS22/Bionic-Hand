# Bionic-Hand.
Folder-ul "Mana" contine piesele 3D folosite pentru alcatuirea protezei.
Folder-ul "Imagini" contine poze facute protezei cat si senzorului.

    Cod:
    #include <Servo.h>
 Servo mare;//min=15, max=160
 Servo mic;//min=10, max=85
 Servo mijlociu;//min=10, max=120
  Servo arat; //min=10, max=110
  Servo inelar;//min=5, max=110
  int senzor=0;
  int senzor1=1;
  int marem,aratm,mijm,inelm,micm;
  int x;
  int y;

  void corec()
  {
    
      marem=x*120/600;
      aratm=x*120/600;
      mijm=x*120/600;
      inelm=x*120/600;
       micm=x*120/600;
      
  }
 
  void setup() 
  {
  mare.attach(14);
  mic.attach(18);
  mijlociu.attach(16);
  arat.attach(15);
  inelar.attach(17);

  Serial.begin(300);
  }
  void loop() 
  { 
   x=analogRead(senzor);
   Serial.print("x=");
   Serial.println(x);
   corec();
    mare.write(marem); 
    arat.write(aratm);
    mijlociu.write(mijm);
    inelar.write(inelm); 
    mic.write(micm);
    
    y=x; 
    delay(100);
  }
