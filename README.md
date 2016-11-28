# first
vamo a darle

package pecman;
//import ucigame.Sprite;

import ucigame.*;
/**
 *
 * @author erick
 */
public class PecMan extends ucigame.Ucigame{
   private Sprite pacman;
   private Sound sonido;
   final int ancho=700,alto=600;
    
    //
    //
      @Override
    public void setup(){
      
       
      //sonido = getSound("sonido/pacman_chomp.wav");
        
     //   sonido.loop();
      window.size(ancho, alto);
     
       window.title("Pac-Man");
        //window.showFPS();
      /*  canvas.background(getImage("images/fondo.jpg"));*/
        //===============================================
        
        }
  
   window.size(ancho, alto);
    
    
    public static void main(String[] args) {
         String params[] = {"pecman.PecMan"};
        ucigame.Ucigame.main(params);
    }
    
}

