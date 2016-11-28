# first
vamo a darle

package pecman;


import java.util.Scanner;
import ucigame.*;
/**
 *
 * @author erick
 */
public class PecMan extends ucigame.Ucigame{
   private Sprite pacman;
   private Sprite fantasmaR;
   private Sprite fantasmaPink;
   private Sprite fantasmaV;
   private Sprite fantasmaC;
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
        fantasmaR.defineSequence("mov", 0, 1);
        
        fantasmaR.play("mov");
        fantasmaR.framerate(16);
        
        
        ///////////// ROSA
        Image ghostPink = getImage("imagenes/fantasmarosa.png");
        fantasmaPink = makeSprite(15, 50);
        fantasmaPink.addFrames(ghostPink, 
                255, 200,
                270, 200);
        fantasmaPink.defineSequence("mov", 0, 1);
        
        fantasmaPink.play("mov");
        fantasmaPink.framerate(16);
        
        
        //////////////////////////////// VERDE
        
         Image ghostV = getImage("imagenes/fantasmaverde.png");
        fantasmaV = makeSprite(15, 50);
        fantasmaV.addFrames(ghostV, 
                257, 200,
                272, 200);
        fantasmaV.defineSequence("mov", 0, 1);
        
        fantasmaV.play("mov");
        fantasmaV.framerate(16);
        
   
        //////////////////////////////////CAFE
         Image ghostC = getImage("imagenes/fantasmacafe.png");
        fantasmaC = makeSprite(15, 50);
        fantasmaC.addFrames(ghostC, 
                257, 200,
                272, 200);
        fantasmaC.defineSequence("mov", 0, 1);
        
        fantasmaC.play("mov");
        fantasmaC.framerate(16);
        
        
        
        
        
        
        
     /*   Image cara = getImage("imagenes/pac-classic_c-toy.png");
     Sprite C = makeSprite(250,250);
          
           C.addFrame(cara, 100,100);
           C.position(350, 300);*/
      window.size(ancho, alto);
     window.title("Pac-Man");
     
    
    }
    
     @Override
    public void draw(){
        int m_x = mouse.x();
        int m_y = mouse.y();
        
        canvas.clear();
        fantasmaR.nextX(m_x-20);
        fantasmaR.nextY(m_y-40);
        fantasmaR.draw();
    
    }
    public static void main(String[] args) {
        // TODO code application logic here
         String params[] = {"pecman.PecMan"};
        ucigame.Ucigame.main(params);
    }
    
}
