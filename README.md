int s1 =0;
int s2 = 1;
int s3 = 2;
int s4 = 3;
int s5 = 4;   
int s6 = 5;
int s7 = 6;
int lm1 = 7;
int lm2 = 8;
int rm1 = 9;
int rm2 = 10;
const int w = 0;
const int b = 1;
int A;
int B;
int C;
int D;
int E;
int F;
int G;


void setup()
{
 pinMode(s1,INPUT);
 pinMode(s2,INPUT);
 pinMode(s3,INPUT);
 pinMode(s4,INPUT);
 pinMode(s5,INPUT);
 pinMode(s6,INPUT);
 pinMode(s7,INPUT);
 pinMode(lm1,OUTPUT);
 pinMode(lm2,OUTPUT);
 pinMode(rm1,OUTPUT);
 pinMode(rm2,OUTPUT);
}


void loop() 
{
 A = digitalRead(s1); 
 B = digitalRead(s2);
 C = digitalRead(s3);
 D = digitalRead(s4);
 E = digitalRead(s5);
 F = digitalRead(s6);
 G = digitalRead(s7);

if(A == b && B == b && C == b && D == w && E == b && F == b && G == b) //straight line
 {
  forward(); 
 }

if(A == w && B == w && C == b && D == b && E == b && F == b && G == b) // left turn
 {
   left();
 }

if(A == b && B == b &&  C == b && D == b && E == b && F == w && G == w) // right turn
 {
   right();
 }

if(A == b && B == b && C == w && D == w && E == b && F == b && G == b) //left curve
 {
   left_1();
 }

if(A == b && B == b && C == b && D == w && E == w && F == b && G == b) // right curve
 {
   right_1();
 }

if(A == w && B == w && C == b && D == b && E == b && F == w && G == w) // T
 {
   left();
 }

if(A == w && B == w && C == b && D == w && E == w && F == b && G == b) // left T
 {
   left();
 }

if(A == b && B == b && C == b && D == w && E == b && F == w && G == w) // right T
 {
   forward();
 }

if(A == w && B == w && C == b && D == w && E == b && F == w && G == w) // +
 {
   left();
 }

if(A == b && B == b && C == b && D == b && E == b && F == b && G == b) //DEAD END
 {
   left();
 }

if(A == w && B == w && C == w && D == w && E == w && F == w && G == w) //HAULT
 {
   hault();
 }

}


void forward()
{
  
   digitalWrite(lm1,HIGH);
   digitalWrite(lm2,LOW);
   digitalWrite(rm1,HIGH);
   digitalWrite(rm2,LOW);

}

void left()
{
  do
  {
   digitalWrite(lm1,LOW);
   digitalWrite(lm2,HIGH);
   digitalWrite(rm1,HIGH);
   digitalWrite(rm2,LOW);
  }
  while(A != b && B != b  && C != b && D != w && E != b && F != b && G != b);
}

void right()
{
  do
  {
   digitalWrite(lm1,HIGH);
   digitalWrite(lm2,LOW);
   digitalWrite(rm1,LOW);
   digitalWrite(rm2,HIGH);
  }
  while(A != b && B != b  && C != b && D != w && E != b && F != b && G != b);
}

void left_1()
{
  do
  {
   digitalWrite(lm1,LOW);
   digitalWrite(lm2,LOW);
   digitalWrite(rm1,HIGH);
   digitalWrite(rm2,LOW);
  }
  while(A != b && B != b  && C != b && D != w && E != b && F != b && G != b );
}

void right_1()
{
  do
  {
   digitalWrite(lm1,HIGH);
   digitalWrite(lm2,LOW);
   digitalWrite(rm1,LOW);
   digitalWrite(rm2,LOW);
  }
  while(A != b && B != b  && C != b && D != w && E != b && F != b && G != b);
}

void hault()
{
 
   digitalWrite(lm1,LOW);
   digitalWrite(lm2,LOW);
   digitalWrite(rm1,LOW);
   digitalWrite(rm2,LOW);
}







