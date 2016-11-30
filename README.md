# first
vamo a darle

package pecman;


import java.util.Scanner;
import ucigame.*;


/*
 
  @author erick
 
 
 */
 
 //////////////////
 
 
 
 
 
 
 
public class PecMan extends ucigame.Ucigame{
   private Sprite pacman;
   private Sprite fantasmaR,fantasmaR1,fantasmaR2,fantasmaR3;
   private Sprite fantasmaPink,fantasmaPink1,fantasmaPink2,fantasmaPink3;
   private Sprite fantasmaV,fantasmaV1,fantasmaV2,fantasmaV3;
   private Sprite fantasmaC,fantasmaC1,fantasmaC2,fantasmaC3;
   private Sprite C,CDer,CIzq,nuca; 
   private Sound sonido;
   final int ancho=700,alto=600;
    
    //
    //
      @Override
    public void setup(){
        Image ghost = getImage("imagenes/fantasmarojo.png");
        
        fantasmaR = makeSprite(15, 50);
        fantasmaR.addFrames(ghost, 
                225, 200,
                240, 200);
        fantasmaR.defineSequence("movl", 0, 1);
        fantasmaR.position(150, 300);
        fantasmaR.play("movl");
        fantasmaR.framerate(30);
        //Hacia otro lado
        fantasmaR1 = makeSprite(15, 50);
        fantasmaR1.addFrames(ghost, 
                257, 200,
                272, 200);
        fantasmaR1.defineSequence("movl", 0, 1);
        fantasmaR1.position(170, 300);
        fantasmaR1.play("movl");
        fantasmaR1.framerate(10);
        //Otro ladp
        fantasmaR2 = makeSprite(15, 50);
        fantasmaR2.addFrames(ghost, 
                288, 200,//288
                305, 200);
        fantasmaR2.defineSequence("movl", 0, 1);
        fantasmaR2.position(190, 300);
        fantasmaR2.play("movl");
        fantasmaR2.framerate(10); 
        ////Ultimo lado del rojo
        fantasmaR3 = makeSprite(15, 50);
        fantasmaR3.addFrames(ghost, 
                321, 200,//288
                337, 200);
        fantasmaR3.defineSequence("movl", 0, 1);
        fantasmaR3.position(210, 300);
        fantasmaR3.play("movl");
        fantasmaR3.framerate(10); 
        ///////////// ROSA
        Image ghostPink = getImage("imagenes/fantasmarosa.png");
        fantasmaPink = makeSprite(15, 50);
        fantasmaPink.addFrames(ghostPink, 
                255, 200,
                270, 200);
        fantasmaPink.defineSequence("mov", 0, 1);
        fantasmaPink.position(150, 150);
        fantasmaPink.play("mov");
        fantasmaPink.framerate(16);
        
        
        fantasmaPink1 = makeSprite(15, 50);
        fantasmaPink1.addFrames(ghostPink, 
                287, 200,
                303, 200);
        fantasmaPink1.defineSequence("mov", 0, 1);
        fantasmaPink1.position(170, 150);
        fantasmaPink1.play("mov");
        fantasmaPink1.framerate(16);
        
        
        fantasmaPink2 = makeSprite(15, 50);
        fantasmaPink2.addFrames(ghostPink, 
                319, 200,
                335, 200);
        fantasmaPink2.defineSequence("mov", 0, 1);
        fantasmaPink2.position(190, 150);
        fantasmaPink2.play("mov");
        fantasmaPink2.framerate(16);
        
        
        fantasmaPink3 = makeSprite(15, 50);
        fantasmaPink3.addFrames(ghostPink, 
                350, 200,//350
                367, 200);
        fantasmaPink3.defineSequence("mov", 0, 1);
        fantasmaPink3.position(210, 150);
        fantasmaPink3.play("mov");
        fantasmaPink3.framerate(16);
        
        //////////////////////////////// VERDE //////////////////////
        
         Image ghostV = getImage("imagenes/fantasmaverde.png");
        fantasmaV = makeSprite(15, 50);
        fantasmaV.addFrames(ghostV, 
                257, 200,
                272, 200);
        fantasmaV.defineSequence("mov", 0, 1);
        fantasmaV.position(150, 250);
        fantasmaV.play("mov");
        fantasmaV.framerate(16);
        
        
        fantasmaV1 = makeSprite(15, 50);
        fantasmaV1.addFrames(ghostV, 
                287, 200,
                304, 200);
        fantasmaV1.defineSequence("mov", 0, 1);
        fantasmaV1.position(170, 250);
        fantasmaV1.play("mov");
        fantasmaV1.framerate(16);
        
        fantasmaV2 = makeSprite(15, 50);
        fantasmaV2.addFrames(ghostV, 
                320, 200,//319
                337, 200);
        fantasmaV2.defineSequence("mov", 0, 1);
        fantasmaV2.position(190, 250);
        fantasmaV2.play("mov");
        fantasmaV2.framerate(16);
        
        fantasmaV3 = makeSprite(15, 50);
        fantasmaV3.addFrames(ghostV, 
                353, 200,
                370, 200);
        fantasmaV3.defineSequence("mov", 0, 1);
        fantasmaV3.position(210, 250);
        fantasmaV3.play("mov");
        fantasmaV3.framerate(16);
        
   
        //////////////////////////////////CAFE
         Image ghostC = getImage("imagenes/fantasmacafe.png");
        fantasmaC = makeSprite(15, 50);
        fantasmaC.addFrames(ghostC, 
                257, 200,
                272, 200);
        fantasmaC.defineSequence("mov", 0, 1);
        fantasmaC.position(150, 200);
        fantasmaC.play("mov");
        fantasmaC.framerate(16);
        
        
        fantasmaC1 = makeSprite(15, 50);
        fantasmaC1.addFrames(ghostC, 
                289, 200,
                306, 200);
        fantasmaC1.defineSequence("mov", 0, 1);
        fantasmaC1.position(170, 200);
        fantasmaC1.play("mov");
        fantasmaC1.framerate(16);
        
        fantasmaC2 = makeSprite(15, 50);
        fantasmaC2.addFrames(ghostC, 
                320, 200,
                337, 200);
        fantasmaC2.defineSequence("mov", 0, 1);
        fantasmaC2.position(190, 200);
        fantasmaC2.play("mov");
        fantasmaC2.framerate(16);
        
        fantasmaC3 = makeSprite(15, 50);
        fantasmaC3.addFrames(ghostC, 
                352, 200,//352
                368, 200);
        fantasmaC3.defineSequence("mov", 0, 1);
        fantasmaC3.position(210, 200);
        fantasmaC3.play("mov");
        fantasmaC3.framerate(16);
        
        
        
        
        
        
        Image cara = getImage("imagenes/carafrente1.png");
        
           C= makeSprite(25,34);
          
           C.addFrames(cara,
                   35,15,
                   60,15 
                    );
           C.defineSequence("movi", 0,1);
           C.play("movi");
           C.position(350, 300);
           C.framerate(30);
           
           
           
        Image carader = getImage("imagenes/caraderecha.png");
        
           CDer= makeSprite(25,25);
          
           CDer.addFrames(carader,
                   15,60,
                   43,60 
                    );
           CDer.defineSequence("movi", 0,1);
           CDer.play("movi");
           CDer.position(350, 200);
           CDer.framerate(7);
           
           
           
        Image caraizq = getImage("imagenes/caraizquierda.png");
        
           CIzq= makeSprite(25,25);
          
           CIzq.addFrames(caraizq,
                   15,60,
                   55,60 
                    );
           CIzq.defineSequence("movi", 0,1);
           CIzq.play("movi");
           CIzq.position(250, 200);
           CIzq.framerate(7);   
        
           
         Image caratras = getImage("imagenes/atras.png");
        
           nuca= makeSprite(25,25);  
           nuca.addFrame(caratras, 35, 60);
           nuca.position(250, 306);
           
     window.size(ancho, alto);
     window.title("Pac-Man");
     
    
    }
    
     @Override
    public void draw(){
        int m_x = mouse.x();
        int m_y = mouse.y();
        
        canvas.clear();
     //   fantasmaR.nextX(m_x-20);
     //   fantasmaR.nextY(m_y-40);
        fantasmaR.draw();fantasmaR2.draw();fantasmaR3.draw();
        C.draw();
        CDer.draw();
        CIzq.draw();
        nuca.draw();
        fantasmaC.draw();
        fantasmaPink.draw();fantasmaPink1.draw();fantasmaPink2.draw();fantasmaPink3.draw();
        fantasmaV.draw();fantasmaV1.draw();fantasmaV2.draw();fantasmaV3.draw();
        fantasmaR1.draw();fantasmaC1.draw();fantasmaC2.draw();fantasmaC3.draw();
          
    }
    public static void main(String[] args) {
        // TODO code application logic here
         String params[] = {"pecman.PecMan"};
        ucigame.Ucigame.main(params);
    }
    
}
