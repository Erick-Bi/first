# first
vamo a darle
//DONE BY ERICK,LUIS & RUBEN
package paca;
import javax.swing.JOptionPane;
import ucigame.*;

//Ultimo

public class PacMan extends Ucigame {

//Definicion de variables

    final private int w=700, h=700;
    
    private int x=0;
    
    private Sprite pacman;
    
    private Sprite comida;
    
    private Sprite Fan1,Fan2,Fan3,Fan4; /// VARIABLES QUE ALMACENARAN FANTASMAS ///
    private Sprite muralla;
    
    private Sound sonido;
    
    private Sound game;
    
    private Sound sony;
    
    private Tablero tabla[];
    
    private comidas Comida[];
   
    private int valory=500;
    
    private int valorx=500;
    
    private int valorxx;
    
    private int valoryy;
    
    private int posicion_ini=0;
    
    private int count;
    
    private int puntuacion=0;
    
    private int contador=0;
    
    private int F1xx;
    
    private int F2xx;
    
    private int F3xx;
    
    private int F1yy;
    
    private int F2yy;
    
    private int F3yy;
    
    ////////////////////////////////////
    ///                              ///
    /// COORDENADAS DE CADA FANTASMA ///
    ///                              ///
    ////////////////////////////////////
    
   int F1x=600,F1y=215;
                                   
   int F2x=68,F2y=30;             
                                 
   int F3x=380,F3y=135;           
   
   
  
   
   @Override
    public void setup(){
         
        
        Image barras =getImage("imagenes/barra.png");
        Image comidas =getImage("imagenes/Comida.png");
        Image imagen =getImage("imagenes/pacman.png");
        Image murallas=getImage("imagenes/muralla.png");
        
        /// DIRECCION DE LA IMAGEN ///
      Image I= getImage("imagenes/pacman.png"); /// LA IMAGEN COMPLETA SE GUARDA EN I ///// 
      
      ////////////  FANTASMA ROJO    ///////////////////
      
      Fan1=makeSprite(20,25); ////// FANTASMAS SE RECORTARAN DE 20 X 25 ///////
      
      Fan1.addFrames(I,0,0,  
                       20,0,  //// POSICIIONES DONDE SE RECORTARAN LAS IMAGENES /////
                       40,0,
                       60,0);
    
      Fan1.defineSequence("Rabajo", 0);   /// LA IMAGEN EN LA POSICION 0  SERA RABAJO ////
      Fan1.defineSequence("Rarriba", 1);
      Fan1.defineSequence("Rizq", 2);
      Fan1.defineSequence("Rder", 3);
      Fan1.framerate(5);
      Fan1.position(F1x, F1y);
      
      ////////////  FANTASMA ROSA ///////////////////////
      
      Fan2=makeSprite(20,25);
      
      Fan2.addFrames(I, 0,25,
                        20,25,
                        40,25,
                        60,25);
      
      Fan2.defineSequence("Pabajo", 0);
      Fan2.defineSequence("Parriba", 1);
      Fan2.defineSequence("Pizq", 2);
      Fan2.defineSequence("Pder", 3);     
      Fan2.framerate(5);
      Fan2.position(F2x, F2y);
      
        ////////////  FANTASMA AZUL ///////////////////////
      
      Fan3=makeSprite(20,25);
      Fan3.addFrames(I, 0,50, 
                       20,49,
                       40,49,
                       60,49);
      Fan3.defineSequence("Aabajo", 0);
      Fan3.defineSequence("Aarriba", 1);
      Fan3.defineSequence("Aizq", 2);
      Fan3.defineSequence("Ader", 3);    
      Fan3.framerate(5);
      Fan3.position(F3x, F3y);

      
        //Comida de pacman
        Comida = new comidas[56]; // Creacion

        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,30);
            Comida[0]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,90);
            Comida[1]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,150);
            Comida[2]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,210);
            Comida[3]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,270);
            Comida[4]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,330);
            Comida[5]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,390);
            Comida[6]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,450);
            Comida[7]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,510);
            Comida[8]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,560);
            Comida[9]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(25,620);
            Comida[10]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(85,30);
            Comida[11]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(145,30);
            Comida[12]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(205,30);
            Comida[13]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(265,30);
            Comida[14]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(325,30);
            Comida[15]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(385,30);
            Comida[16]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(445,30);
            Comida[17]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(505,30);
            Comida[18]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(565,30);
            Comida[19]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(625,30);
            Comida[20]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,100);
            Comida[21]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,160);
            Comida[22]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,220);
            Comida[23]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,280);
            Comida[24]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,340);
            Comida[25]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,400);
            Comida[26]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,460);
            Comida[27]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,520);
            Comida[28]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,580);
            Comida[29]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(630,640);
            Comida[30]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(570,630);
            Comida[31]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(510,630);
            Comida[32]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(450,630);
            Comida[33]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(390,630);
            Comida[34]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(330,630);
            Comida[35]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(270,630);
            Comida[36]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(210,630);
            Comida[37]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(150,630);
            Comida[38]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(90,630);
            Comida[39]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(365,100);
            Comida[40]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(365,200);
            Comida[41]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(365,300);
            Comida[42]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(365,400);
            Comida[43]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(365,500);
            Comida[44]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(245,500);
             Comida[45]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(125,500);
            Comida[46]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(565,500);
            Comida[47]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(485,85);
            Comida[48]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(485,145);
            Comida[49]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(485,205);
            Comida[50]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(485,265);
            Comida[51]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(485,325);
            Comida[52]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(485,385);
            Comida[53]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(110,370);
            Comida[54]=new comidas(comida);
        comida=makeSprite(40,40);
        comida.addFrame(comidas,0, 0);
        comida.position(250,370);
            Comida[55]=new comidas(comida);
            
        //Movimientos de pacman 
        //izquierdo 
        //=========================================
        pacman = makeSprite(20, 25);
        pacman.addFrames(imagen, 
                80, 0,
                80, 25,
                80, 50,
                80, 75,
                80, 100,
                80, 125,
                100,0);
        pacman.defineSequence("izq",2,4);
        pacman.defineSequence("der",1,3);
        pacman.defineSequence("arriba",5);
        pacman.defineSequence("abajo",0,6);
        pacman.framerate(10);
        pacman.position(valorx,valory);
       
        
     
        //Muralla=====================================================================================================================================
        
     
        tabla = new Tablero[17];
        
        //arriba
        //========================================
        muralla=makeSprite(700,25);
        muralla.addFrame(murallas, 0, 0);
        muralla.position(0,0);
        tabla[0] = new Tablero(muralla);
        //abajo
        //===========================================
        muralla=makeSprite(700,25);
        muralla.addFrame(murallas,0, 675);
        muralla.position(0,675);
        tabla[1] = new Tablero(muralla);
        //izquierda
        //==========================================
        muralla=makeSprite(25,675);
        muralla.addFrame(murallas,0, 25);
        muralla.position(0,25);
        tabla[2] = new Tablero(muralla);
        //derecho
        //============================================
        muralla=makeSprite(25,650);
        muralla.addFrame(murallas,675, 25);
        muralla.position(675,25);
        tabla[3] = new Tablero(muralla);
        //Centro
        //=============================================
        muralla =makeSprite(300,300);
        muralla.addFrame(murallas,100, 100);
        muralla.position(65,65);
        tabla[4] = new Tablero(muralla);
        
        
        //barras centrales
        muralla =makeSprite(200,20);
        muralla.addFrame(barras,20, 0);
        muralla.position(410,65);
        tabla[5] = new Tablero(muralla);
        
        muralla =makeSprite(20,200);
        muralla.addFrame(barras,0, 0);
        muralla.position(410,65);
        tabla[6] = new Tablero(muralla);
        
        muralla =makeSprite(160,20);
        muralla.addFrame(barras,40, 40);
        muralla.position(470,125);
        tabla[7] = new Tablero(muralla);
        
        muralla =makeSprite(160,20);
        muralla.addFrame(barras,40, 40);
        muralla.position(470,185);
        tabla[8] = new Tablero(muralla);
        
        muralla =makeSprite(160,20);
        muralla.addFrame(barras,40, 40);
        muralla.position(470,245);
        tabla[9] = new Tablero(muralla);
        
        
        muralla =makeSprite(200,20);
        muralla.addFrame(barras,20, 0);
        muralla.position(85,410);
        tabla[10] = new Tablero(muralla);
        
        muralla =makeSprite(20,200);
        muralla.addFrame(barras,0, 0);
        muralla.position(65,410);
        tabla[11] = new Tablero(muralla);
        
        muralla =makeSprite(20,180);
        muralla.addFrame(barras,200, 20);
        muralla.position(610,425);
        tabla[12] = new Tablero(muralla);
        
        muralla =makeSprite(180,20);
        muralla.addFrame(barras,20, 180);
        muralla.position(435,585);
        tabla[13] = new Tablero(muralla);
        
        
        muralla =makeSprite(160,20);
        muralla.addFrame(barras,40, 40);
        muralla.position(470,305);
        tabla[14] = new Tablero(muralla);
       
        muralla =makeSprite(160,20);
        muralla.addFrame(barras,40, 40);
        muralla.position(470,365);
        tabla[15] = new Tablero(muralla);
        
         muralla =makeSprite(160,20);
        muralla.addFrame(barras,40, 40);
        muralla.position(400,425);
        tabla[16] = new Tablero(muralla);
      //Muralla=====================================================================================================================================
        
        //======================================
        //sonido
        //================================
        sony=getSound("Sony.wav");
        sony.play();
       
        sonido = getSound("fondo1.wav");
        game =getSound("game.wav");
       
        
        //====================================================
        //Ventana
         window.size(w, h);
         window.title("PacMan");
         

        canvas.background(getImage("imagenes/Menu.png")); //Fondo
        framerate(30);
       
        
        
        
    }
    
    private int contarVivos(){
        int count = 0;
        for(comidas tacos:Comida){
            if(tacos.isVivo()){
                count++;
            }
            
        }
        return count;
    }
        
      
    
   
    @Override
    public void draw(){
        
      
      int vivos = contarVivos();
      window.title("Quedan: "+ vivos);
      if(vivos<=0){
            sonido.stop();
            game.play();
            JOptionPane.showMessageDialog(null, "Puntuación: " + contador + " \nGAME OVER");
            
            game.stop();
            System.exit(0);
        }
     
        
     
    //  System.out.printf("%d---%d\n", valorx,valory);//COORDENADAS
      canvas.clear();
      if(posicion_ini==0){
       Fan1.play("Rabajo");
       Fan1.draw();
       
       Fan2.play("Pabajo");
       Fan2.draw();
       
       Fan3.play("Aabajo");
       Fan3.draw();
       
       pacman.play("abajo");
       pacman.draw();
          
      }
      
      ////==========================================================================================
      
     
            //////////// FANTASMA ROJO ////////////////
           
        
          if(valorx<F1x&&posicion_ini!=0){
               F1xx=F1x;     //Para obtener la posicion un instante antes del choque
              
              Fan1.position(F1x-=3, F1y);  //Decrecrementa la posicion en x 
              if(F1x<=valorx)  //si el fantasma se pasa un poco lo iguala a la posicion de pacman
              F1x=valorx;
              Fan1.play("Rizq");  //dibuja el fan a la izquierda
              ///===================================================
              
            for(Tablero tablas: tabla){   //Checamos si hay colicion con algun muro
              Fan1.checkIfCollidesWith(tablas.getSprite());
              if(Fan1.collided()){  //Si colisiona 
                     F1x=F1xx;    //La posicion en x se guanda un instante antes
                     if(F1y>25&&F1y>valory){ //Determina hacia donde ir el fan
                     F1y -=3;         // dependiendo de la posicion vertical de pacman
                     Fan1.play("Rarriba");
                     }
                     else{
                     F1y +=3;
                     Fan1.play("Rabajo");
                     }
                     
                     
              }
              }
                    
              Fan1.draw();
           }
          else if (valorx>F1x&&posicion_ini!=0){//si fantasma a la izquierda
              F1xx=F1x;
              Fan1.position(F1x+=3, F1y);//lo sigue a la derecha
              if(F1x>=valorx)
              F1x=valorx;
              Fan1.play("Rder");
              for(Tablero tablas: tabla){   //checamos si hay colicion con algun muro
              Fan1.checkIfCollidesWith(tablas.getSprite());
              if(Fan1.collided()){
                     F1x=F1xx;
                     if(F1y<650&&F1y<valory){
                     F1y +=3; 
                     Fan1.play("Rabajo");
                     }
                     else{
                     F1y -=3;
                     Fan1.play("Rarriba");
                     }
                     Fan1.play("Rabajo");
              }
              }
              Fan1.draw();
          }
          else{
           if(valory>F1y&&posicion_ini!=0){//si fantasma arriba
                        F1yy=F1y;
                        Fan1.position(F1x, F1y+=3);//lo sigue hacia abajo
                        Fan1.play("Rabajo");
                        for(Tablero tablas: tabla){   //checamos si hay colicion con algun muro
                            Fan1.checkIfCollidesWith(tablas.getSprite());
                            if(Fan1.collided()){
                                F1y=F1yy;
                                
                            }
                        }
                        Fan1.draw();
                                  }
           else if (valory<F1y&&posicion_ini!=0){//fantasma abajo
                        F1yy=F1y;
                        Fan1.position(F1x, F1y-=3);//lo sigue para arriba
                        Fan1.play("Rarriba");
                        for(Tablero tablas: tabla){   //checamos si hay colicion con algun muro
                            Fan1.checkIfCollidesWith(tablas.getSprite());
                            if(Fan1.collided()){
                                F1y=F1yy;
                                
                            }
                        }
                        Fan1.draw();
                                
            }    
          }
         
           
            //////////// FANTASMA ROSA ////////////////
           
          
         if(valorx<F2x&&posicion_ini!=0){//si fantasma esta a la derecha
               F2xx=F2x;     //Para obtener la posicion un instante antes del choque
              
              Fan2.position(F2x-=3, F2y);  //Decrecrementa la posicion en x 
              if(F2x<=valorx)  //si el fantasma se pasa un poco lo iguala a la posicion de pacman
              F2x=valorx;
              Fan2.play("Pizq");  //dibuja el fan a la izquierda
              ///===================================================
              
            for(Tablero tablas: tabla){   //Checamos si hay colicion con algun muro
              Fan2.checkIfCollidesWith(tablas.getSprite());
              if(Fan2.collided()){  //Si colisiona 
                     F2x=F2xx;    //La posicion en x se guanda un instante antes
                     if(F2y>25&&F2y>valory){ //Determina hacia donde ir el fan
                     F2y -=3;         // hacia arriba
                     Fan2.play("Parriba");
                     }
                     else{
                     F2y +=3;//hacia abajo
                     Fan2.play("Pabajo");
                     }
                     
                     
              }
              }
                    
              Fan2.draw();
           }
          else if (valorx>F2x&&posicion_ini!=0){//si fantasma esta en la izquierda
              F2xx=F2x;
              Fan2.position(F2x+=3, F2y);//lo sigue a la derecha
              if(F2x>=valorx)
              F2x=valorx;
              Fan2.play("Pder");
              for(Tablero tablas: tabla){   //si colociona con el muro
              Fan2.checkIfCollidesWith(tablas.getSprite());
              if(Fan2.collided()){
                     F2x=F2xx;
                     if(F2y<650&&F2y<valory){// lo sigue hacia abajo
                     F2y +=3; 
                     Fan2.play("Pabajo");
                     }
                     else{//si no hacia arriba
                     F2y -=3;
                     Fan2.play("Parriba");
                     }
                     Fan2.play("Pabajo");
              }
              }
              Fan2.draw();
          }
          else{
           if(valory>F2y&&posicion_ini!=0){// si el fantasma esta arriba
                        F2yy=F2y;
                        Fan2.position(F2x, F2y+=3);//fantasma hacia abajo
                        Fan2.play("Pabajo");
                        for(Tablero tablas: tabla){   //colicion muro
                            Fan2.checkIfCollidesWith(tablas.getSprite());
                            if(Fan2.collided()){
                                F2y=F2yy;
                                
                            }
                        }
                        Fan2.draw();
                                  }
           
           else if (valory<F2y&&posicion_ini!=0){//si fantasma esta abajo
                        F2yy=F2y;
                        Fan2.position(F2x, F2y-=3); //fantasma lo sigue para arriba
                        Fan2.play("Parriba");
                        for(Tablero tablas: tabla){   //colicion con algun muro
                            Fan2.checkIfCollidesWith(tablas.getSprite());
                            if(Fan2.collided()){
                                F2y=F2yy;//si colisiona se queda en la posicion anterior
                                
                            }
                        }
                        Fan2.draw();
                                
            }    
          }
          
           //////////// FANTASMA AZUL ///////////////
           
          
         if(valorx<F3x&&posicion_ini!=0){//si el fantasma esta a la derecha
               F3xx=F3x;     //Toma posicion antes del choque
              
              Fan3.position(F3x-=3, F3y);  //Decrecrementa la posicion en x 
              if(F3x<=valorx)  //si es menor la posicion del fantasma lo iguala al de pacman en x
              F3x=valorx;
              Fan3.play("Aizq");
              ///===================================================
              
            for(Tablero tablas: tabla){   // si coliciona con muro
              Fan3.checkIfCollidesWith(tablas.getSprite());
              if(Fan3.collided()){  
                     F3x=F3xx;    //se guarad en pixeles antes
                     if(F3y>25&&F3y>valory){ //SI se cumple
                     F3y -=3;         // Lo persigue hacia arriba
                     Fan3.play("Aarriba");
                     }
                     else{
                     F3y +=3;  //Lo persigue hacia abajo
                     Fan3.play("Aabajo");
                     }
                     
                     
              }
              }
                    
              Fan3.draw();
           }
          else if (valorx>F3x&&posicion_ini!=0){ //si el fantasma esta a la izquierda
              F3xx=F3x;
              Fan3.position(F3x+=3, F3y);
              if(F3x>=valorx)
              F3x=valorx;
              Fan3.play("Ader");
              for(Tablero tablas: tabla){  
              Fan3.checkIfCollidesWith(tablas.getSprite());
              if(Fan3.collided()){
                     F3x=F3xx;
                     if(F3y<650&&F3y<valory){
                     F3y +=3; 
                     Fan3.play("Aabajo");
                     }
                     else{
                     F3y -=3;
                     Fan3.play("Aarriba");
                     }
                     Fan3.play("Aabajo");
              }
              }
              Fan3.draw();
          }
          else{
           if(valory>F3y&&posicion_ini!=0){//Si el fantasma esta arriba
                        F3yy=F3y;
                        Fan3.position(F3x, F3y+=3);//lo sigue hacia abajo
                        Fan3.play("Aabajo");
                        for(Tablero tablas: tabla){   //colicion con el muro
                            Fan3.checkIfCollidesWith(tablas.getSprite());
                            if(Fan3.collided()){
                                F3y=F3yy;
                                
                            }
                        }
                        Fan3.draw();
                                  }
           
           else if (valory<F3y&&posicion_ini!=0){//Si el fantasma esta abajo
                        F3yy=F3y;
                        Fan3.position(F3x, F3y-=3);//Fanatasma va hacia arriba
                        Fan3.play("Aarriba");
                        for(Tablero tablas: tabla){   //checamos colicion con  muro
                            Fan3.checkIfCollidesWith(tablas.getSprite());
                            if(Fan3.collided()){
                                F3y=F3yy;
                                
                            }
                        }
                        Fan3.draw();
                                
            }    
          }
         
         
          Fan1.checkIfCollidesWith(pacman); //checamos si algun fantasma choca con pacman
          Fan2.checkIfCollidesWith(pacman);
          Fan3.checkIfCollidesWith(pacman);
          if(Fan1.collided()||Fan2.collided()||Fan3.collided()){   //colision con pacman cara derecha
                 sonido.stop();
                 game.play();
                 JOptionPane.showMessageDialog(null, "Puntuación: " + contador + " \nGAME OVER");
            
             
                 game.stop();
                 System.exit(0);
          }    
         
    
         
      //===================================================================================================
      
      //=======================================================
      //Movimiento hacia la izquierda
      //======================================================
      if(keyboard.key()==keyboard.LEFT){
          valorxx=valorx;
          if(x==0){
           sonido.stop();
           sonido = getSound("pacman_chomp.wav");
           sonido.loop();
          x=1;
          }
            

          valorx -=5;
          
          if(valorx>25){
          
          pacman.nextX(valorx);
          }else
              valorx=25;
           
          for(Tablero tablas: tabla){
              pacman.checkIfCollidesWith(tablas.getSprite());
              if(pacman.collided()){
                  valorx=valorxx;
                  pacman.position(valorx, valory);
                  pacman.pauseIfCollidesWith(pacman);
              }
          }
           
          pacman.play("izq");
          pacman.draw();
          posicion_ini=1;
         
          
            
           
      }
      //======================================================
      //Movimiento hacia la derecha
      //======================================================
      if(keyboard.key()==keyboard.RIGHT){
           valorxx=valorx;
          if(x==0){
           sonido.stop();
           sonido = getSound("pacman_chomp.wav");
           sonido.loop();
          x=1;
          }
              
          valorx +=5;
          if(valorx<w-45){
          
          pacman.nextX(valorx);
          }
          else
              valorx=w-45;
           
          
          for(Tablero tablas: tabla){
              pacman.checkIfCollidesWith(tablas.getSprite());
              if(pacman.collided()){
                  valorx=valorxx;
                  pacman.position(valorx, valory);
                  pacman.pauseIfCollidesWith(pacman);
              }
          }
           pacman.play("der");
           pacman.draw();
          posicion_ini=1;
         
         
            
      }
      //======================================================
      //Movimiento hacia arriba
      //======================================================
      if(keyboard.key()==keyboard.UP){
           valoryy=valory;//guarda un instante antes del choque
          if(x==0){
           sonido.stop();
           sonido = getSound("pacman_chomp.wav");
           sonido.loop();
          x=1;
          }
          valory -=5;
          
          if(valory>25){
          
          
          pacman.nextY(valory);
          }
          else{
              valory=25;
          }
          for(Tablero tablas: tabla){
              pacman.checkIfCollidesWith(tablas.getSprite());
              if(pacman.collided()){
                  valory=valoryy;
                  pacman.position(valorx, valory);
                  pacman.pauseIfCollidesWith(pacman);
              }
          }
         
          pacman.play("arriba");
          pacman.draw();
          posicion_ini=1;
    
            
      }
      
      //==========================================================
      //Movimiento hacia abajo    
      //======================================================
      if(keyboard.key()==keyboard.DOWN){
           valoryy=valory;
          if(x==0){
           sonido.stop();
           sonido = getSound("pacman_chomp.wav");
           sonido.loop();
          x=1;
          }
          
          valory +=5;
          if(valory<h-50){
              
          pacman.nextY(valory);
          }
          else
              valory=h-50;
          for(Tablero tablas: tabla){
              pacman.checkIfCollidesWith(tablas.getSprite());
              if(pacman.collided()){
                  valory=valoryy;
                  pacman.position(valorx, valory);
                  pacman.pauseIfCollidesWith(pacman);
              }
          }
   
          pacman.play("abajo");
          pacman.draw();
          posicion_ini=1;
     
    
            
      }   
      //============================================================
      //Construccion del tablero
     //======================================================
   
  for(Tablero tablita:tabla){
        tablita.getSprite().draw();
  }
  for(comidas taco:Comida){
      
        taco.getSprite().checkIfCollidesWith(pacman);
        if(taco.getSprite().collided()){
            Sound s = getSound("comiendo.wav");
            s.play();
            taco.matar();
            contador=contador+5;
            taco.getSprite().position(1000, 1000);
        } 
        if (taco.isVivo()){
        taco.getSprite().draw();
        
        }
           
             
    }

    }
    
    public static void main(String[] args) {
       String params[] = {"paca.PacMan"};
        Ucigame.main(params);
    }
    
}

/////////////////////////////////////////////////////
/* La Clase Tablero  */

package paca;
import ucigame.*;

class Tablero {  //solo paquete y clase
    private final Sprite sprite;
    
    
    Tablero( Sprite s) { 
        sprite = s;
        
    }
    
    protected Sprite getSprite(){ //todos menos los otros
        return sprite;
    }
    
   
    
   
}

///////////////////////////////////////////////////////
/* La Clase Comidas*/

package paca;

import ucigame.*;

  class comidas {
    private boolean vivo;
    private final Sprite sprite;
    
    protected comidas( Sprite s) {
        sprite = s;
        vivo = true;
    }
    
    
    protected Sprite getSprite(){
        return sprite;
    }
    
    protected boolean isVivo(){
        return vivo;
    }
    
    protected void matar(){
        vivo = false;
    }
}    
