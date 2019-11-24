# gundamDrawingJavaFX(drawing code of gundam)

package gundam;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.util.Random;

import javafx.animation.FadeTransition;
import javafx.animation.FillTransition;
import javafx.animation.KeyFrame;
import javafx.animation.KeyValue;
import javafx.animation.PauseTransition;
import javafx.animation.RotateTransition;
import javafx.animation.ScaleTransition;
import javafx.animation.SequentialTransition;
import javafx.animation.Timeline;
import javafx.animation.TranslateTransition;
import javafx.application.Application;
import javafx.scene.Group;
import javafx.scene.Node;
import javafx.scene.Scene;
import javafx.scene.effect.BoxBlur;
import javafx.scene.effect.Light;
import javafx.scene.effect.Lighting;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.image.PixelReader;
import javafx.scene.image.PixelWriter;
import javafx.scene.image.WritableImage;
import javafx.scene.layout.Pane;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.paint.CycleMethod;
import javafx.scene.paint.LinearGradient;
import javafx.scene.paint.Stop;
import javafx.scene.shape.Circle;
import javafx.scene.shape.Polygon;
import javafx.scene.shape.Shape;
import javafx.stage.Stage;
import javafx.util.Duration;


	public class gundamTryon extends Application { 
////////////////////////////////////////////////////////////////effect circle object/////////////////////////////////////////////////////////////		
		 // Circle colors
	    Color[] colors = {
	        new Color(0.2,0.5,0.8, 1.0).saturate().brighter().brighter(),
	        new Color(0.3,0.2,0.7,1.0).saturate().brighter().brighter(),
	        new Color(0.8,0.3,0.9,1.0).saturate().brighter().brighter(),
	        new Color(0.4,0.3,0.9,1.0).saturate().brighter().brighter(),
	        new Color(0.2,0.5,0.7,1.0).saturate().brighter().brighter()};
	    
    
		   Random random = new Random();
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////		
		   public static void main(String args[]){ 
			      launch(args); 
			   }
//////////////////////////////////////////////////////////////////image background///////////////////////////////////////////////////////////////////////////////
		   public Node image() throws FileNotFoundException {
			   String path = "https://wallpapershome.com/images/wallpapers/saturn-1920x1080-planet-purple-4k-16672.jpg";
			   Image image = new Image(path); 
			  int width = (int)image.getWidth(); 
			      int height = (int)image.getHeight(); 
			         
			     // Creating a writable image 
			      WritableImage wImage = new WritableImage(width, height); 
			         
			      //Reading color from the loaded image 
			      PixelReader pixelReader = image.getPixelReader(); 
			      
			      //getting the pixel writer 
			      PixelWriter writer = wImage.getPixelWriter();           
			      
			     // Reading the color of the image 
			      for(int y = 0; y < height; y++) { 
			         for(int x = 0; x < width; x++) { 
			       //Retrieving the color of the pixel of the loaded image   
			            Color color = pixelReader.getColor(x, y); 
			              
			            //Setting the color to the writable image 
			            writer.setColor(x, y, color.darker());              
			         }
			      }	
			      //Setting the view for the writable image 
			     ImageView imageView = new ImageView(wImage); 
			     return imageView; 
		   }
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
////////////////////////////////////////////////////////////////image logo///////////////////////////////////////////////////////////////////////////////////////////		   
		   public Node logo() throws FileNotFoundException{
			   String path = "https://vignette.wikia.nocookie.net/gundam/images/4/46/Gundam_Build_Fighters_GM%27s_Counterattack_Logo.png/revision/latest?cb=20170727214350";
			   Image image = new Image(path); 
			  int width = (int)image.getWidth(); 
			      int height = (int)image.getHeight(); 
			         
			     // Creating a writable image 
			      WritableImage wImage = new WritableImage(width, height); 
			         
			      //Reading color from the loaded image 
			      PixelReader pixelReader = image.getPixelReader(); 
			      
			      //getting the pixel writer 
			      PixelWriter writer = wImage.getPixelWriter();           
			      
			     // Reading the color of the image 
			      for(int y = 0; y < height; y++) { 
			         for(int x = 0; x < width; x++) { 
			       //Retrieving the color of the pixel of the loaded image   
			            Color color = pixelReader.getColor(x, y); 
			              
			            //Setting the color to the writable image 
			            writer.setColor(x, y, color.darker());              
			         }
			      }	
			      //Setting the view for the writable image 
			     ImageView imageView = new ImageView(wImage); 
			     return imageView; 
			   
		   }
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
///////////////////////////////////////////////////////////////gundam Set/////////////////////////////////////////////////////////////////////////////////////////////////////////		   
		   public Node leftBigAngleOne() {
			   Polygon leftBigAngleOne = new Polygon();
			   leftBigAngleOne.getPoints().addAll(new Double[]{ 
				         580.0, 125.0, 
				         696.0, 349.0, 
				         719.0, 338.0, 
				         813.0,403.0,
				         799.0, 363.0, 
				         694.0,304.0,
				      });
			  
			   	//Instantiating the Light.Distant class
			      Light.Distant light = new Light.Distant(); 
			      
			      //Setting the properties of the light source 
			      light.setAzimuth(45.0); 
			      light.setElevation(30.0);       
			       
			      //Instantiating the Lighting class  
			      Lighting lighting = new Lighting(); 
			      
			      //Setting the source of the light 
			      lighting.setLight(light);

			      	  leftBigAngleOne.setEffect(lighting);	
				      leftBigAngleOne.setFill(Color.YELLOW);
				      leftBigAngleOne.setStroke(Color.BLACK);
				      leftBigAngleOne.setStrokeWidth(2.0);
				      Polygon leftBigAngleTwo = new Polygon();
					   leftBigAngleTwo.getPoints().addAll(new Double[]{ 
						         580.0, 125.0, 
						         710.0, 272.0, 
						         749.0, 293.0, 
						         777.0,330.0,
						         790.0, 311.0, 
						         803.0,320.0,
						         788.0,334.0,
						         799.0,363.0,
						         694.0,304.0,
						      });
					 //Setting the linear gradient 
					      Stop[] stops = new Stop[] { 
					         new Stop(0, Color.GOLD),  
					         new Stop(1, Color.WHITE)
					      };  
					      LinearGradient linearGradient = 
					         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
					      
					      
						      leftBigAngleTwo.setFill(linearGradient);
						      leftBigAngleTwo.setStroke(Color.BLACK);
						      leftBigAngleTwo.setStrokeWidth(2.0);
					
						      Polygon leftSecondAngleOne = new Polygon();
							   leftSecondAngleOne.getPoints().addAll(new Double[]{ 
								         749.0, 293.0, 
								         759.0, 286.0, 
								        677.0, 39.0, 
								         715.0,103.0,
								         773.0, 323.0, 
								        
								      });
							   //Setting the linear gradient 
							      Stop[] stopsTwo = new Stop[] { 
							         new Stop(0, Color.GOLD),  
							         new Stop(1, Color.WHITE)
							      };  
							      LinearGradient linearGradientTwo = 
							         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stopsTwo);     
							     
							         
						      leftSecondAngleOne.setFill(linearGradientTwo);
						      leftSecondAngleOne.setStroke(Color.BLACK);
						      leftSecondAngleOne.setStrokeWidth(2.0);      
						      
				      Group Angle = new Group(leftBigAngleTwo,leftBigAngleOne,leftSecondAngleOne);
				      
				      
				      return Angle;
			   
		   }

		   public Node leftSecondAngleTwo() {
			   Polygon leftSecondAngleTwo = new Polygon();
			   leftSecondAngleTwo.getPoints().addAll(new Double[]{ 
				         677.0,39.0,
				         777.0,140.0,
				         715.0,103.0,
				        
				      });
			   //Setting the linear gradient 
			      Stop[] stops = new Stop[] { 
			         new Stop(0, Color.GOLD),  
			         new Stop(1, Color.WHITE)
			      };  
			      LinearGradient linearGradient = 
			         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
			                
		      leftSecondAngleTwo.setFill(linearGradient);
		      leftSecondAngleTwo.setStroke(Color.BLACK);
		      leftSecondAngleTwo.setStrokeWidth(2.0);
		      return leftSecondAngleTwo;
		   }
		   public Node leftSecondAngleThree() {
			   Polygon leftSecondAngleThree = new Polygon();
			   leftSecondAngleThree.getPoints().addAll(new Double[]{ 
				       777.0,140.0,
				       746.0,129.0,
				       790.0,311.0,
				       777.0,330.0,
				       773.0,323.0,
				       715.0,103.0,
				       
				        
				      });
			   //Instantiating the Light.Distant class
			      Light.Distant light = new Light.Distant(); 
			      
			      //Setting the properties of the light source 
			      light.setAzimuth(45.0); 
			      light.setElevation(30.0);       
			       
			      //Instantiating the Lighting class  
			      Lighting lighting = new Lighting(); 
			      
			      //Setting the source of the light 
			      lighting.setLight(light);
			      
			      leftSecondAngleThree.setEffect(lighting); 
			      
			      leftSecondAngleThree.setFill(Color.YELLOW);
			      leftSecondAngleThree.setStroke(Color.BLACK);
			      leftSecondAngleThree.setStrokeWidth(2.0);
			      return leftSecondAngleThree;
		   }
		   public Node headAngleUpOne() {
			   Polygon headAngleUpOne = new Polygon();
			   headAngleUpOne.getPoints().addAll(new Double[]{ 
					      813.0,317.0,
					      803.0,317.0,
					      785.0,296.0,
					      795.0,205.0,
					      798.0,199.0,
					      804.0,194.0,
					      852.0,176.0,
					      914.0,176.0,
					      918.0,179.0,
					      922.0,184.0,
					      933.0,217.0,
					      924.0,235.0,
					      928.0,262.0,
					      912.0,313.0,
					      898.0,318.0,
					      893.0,315.0,
					      887.0,315.0,
					      869.0,296.0,
					      848.0,208.0,
					      846.0,206.0,
					      843.0,204.0,
					      806.0,204.0,
					      803.0,206.0,
					      800.0,209.0,
					      793.0,297.0,
					       
					        
					      });
			 //Setting the linear gradient 
			      Stop[] stops = new Stop[] { 
			         new Stop(0, Color.rgb(255, 71, 26)),  
			         new Stop(1, Color.DARKRED),
			         
			      };  
			      LinearGradient linearGradient = 
			         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 	
			      headAngleUpOne.setFill(linearGradient);
			      headAngleUpOne.setStroke(Color.BLACK);
			      headAngleUpOne.setStrokeWidth(2.0);
			      return headAngleUpOne;
		   }
		   public Node headAngleUpTwo() {
			   Polygon headAngleUpTwo = new Polygon();
			   headAngleUpTwo.getPoints().addAll(new Double[]{ 
						 813.0,317.0,
						 803.0,317.0,
						 788.0,334.0,
						 813.0,403.0,
						 844.0,442.0,
						 878.0,442.0,
						 902.0,411.0,
						 878.0,364.0,
						 898.0,318.0,
						 893.0,315.0,
						 887.0,315.0,
						 868.0,334.0,
						 852.0,396.0,
						 850.0,399.0,
						 847.0,402.0,
						 823.0,402.0,
						 820.0,400.0,
						 818.0,398.0,
						 797.0,334.0,
						 
						      });
			   //Setting the linear gradient 
			      Stop[] stops = new Stop[] { 
			         new Stop(0, Color.rgb(255, 71, 26)),  
			         new Stop(1, Color.DARKRED),
			         
			      };  
			      LinearGradient linearGradient = 
			         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
				      headAngleUpTwo.setFill(linearGradient);
				      headAngleUpTwo.setStroke(Color.BLACK);
				      headAngleUpTwo.setStrokeWidth(2.0);
				      return headAngleUpTwo;
		   }
		   public Node headSkinHideUpOne() {
			   Polygon headSkinHideUpOne = new Polygon();
			   headSkinHideUpOne.getPoints().addAll(new Double[]{ 
						887.0,315.0,
						869.0,296.0,
						848.0,208.0,
						846.0,206.0,
						843.0,204.0,
						806.0,204.0,
						803.0,206.0,
						800.0,209.0,
						793.0,297.0,
						813.0,317.0,
						
						      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);
		      headSkinHideUpOne.setFill(linearGradient);
		      headSkinHideUpOne.setStroke(Color.BLACK);
		      headSkinHideUpOne.setStrokeWidth(2.0);
		      return headSkinHideUpOne;
				      
		   }
		   public Node headSkinHideDownTwo() {
			   Polygon headSkinHideDownTwo = new Polygon();
			   headSkinHideDownTwo.getPoints().addAll(new Double[]{ 
						887.0,315.0,
						868.0,334.0,//
						 852.0,396.0,
						 850.0,399.0,
						 847.0,402.0,
						 823.0,402.0,
						 820.0,400.0,
						 818.0,398.0,
						 797.0,334.0,
						813.0,317.0,
						
						      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);
		      headSkinHideDownTwo.setFill(linearGradient);
		      headSkinHideDownTwo.setStroke(Color.BLACK);
		      headSkinHideDownTwo.setStrokeWidth(2.0);
		      return headSkinHideDownTwo; 
			   
		   }
		   public Node headEyeOne() {
			   Polygon headEyeOne = new Polygon();
			   headEyeOne.getPoints().addAll(new Double[]{ 
						864.0,281.0,
						849.0,281.0,
						848.0,282.0,
						846.0,283.0,
						845.0,284.0,
						843.0,285.0,
						841.0,286.0,
						839.0,287.0,
						838.0,288.0,
						835.0,291.0,
						834.0,293.0,
						833.0,295.0,
						831.0,297.0,
						830.0,299.0,
						829.0,302.0,
						829.0,304.0,
						829.0,317.0,
						830.0,318.0,
						831.0,321.0,
						832.0,324.0,
						833.0,326.0,
						834.0,328.0,
						836.0,330.0,
						838.0,332.0,
						840.0,334.0,
						842.0,336.0,
						844.0,338.0,
						846.0,338.0,
						849.0,339.0,
						852.0,339.0,
						856.0,339.0,
						861.0,339.0,
						867.0,339.0,
						868.0,334.0,
						887.0,315.0,
						869.0,296.0,
						
						      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      headEyeOne.setFill(linearGradient);
		      headEyeOne.setStroke(Color.BLACK);
		      headEyeOne.setStrokeWidth(2.0);
		      return headEyeOne;
			   
		   }
		   public Node headBrowSkinone() {
			   Polygon headBrowSkinone = new Polygon();
			   headBrowSkinone.getPoints().addAll(new Double[]{ 
						835.0,215.0,
						834.0,215.0,
						833.0,214.0,
						832.0,214.0,
						830.0,214.0,
						828.0,215.0,
						827.0,216.0,
						827.0,218.0,
						828.0,219.0,
						829.0,220.0,
						855.0,273.0,
						856.0,274.0,
						857.0,274.0,
						858.0,273.0,
						858.0,272.0,
						858.0,271.0,
						858.0,269.0,
						
						
						      });
		      headBrowSkinone.setFill(Color.rgb(255, 71, 26));
		      headBrowSkinone.setStroke(Color.BLACK);
		      headBrowSkinone.setStrokeWidth(2.0);
		      return headBrowSkinone;
		   }
		   public Node headBrowSkinTwo() {
			   Polygon headBrowSkinTwo = new Polygon();
			   
			      headBrowSkinTwo.getPoints().addAll(new Double[]{ 
							810.0,220.0,
							809.0,219.0,
							808.0,219.0,
							807.0,219.0,
							806.0,220.0,
							805.0,221.0,
							805.0,222.0,
							805.0,223.0,
							805.0,225.0,
							806.0,226.0,
							839.0,276.0,
							840.0,277.0,
							841.0,277.0,
							842.0,276.0,
							843.0,275.0,
							843.0,274.0,
							842.0,273.0,
							
							
							      });
			      headBrowSkinTwo.setFill(Color.rgb(255, 71, 26));
			      headBrowSkinTwo.setStroke(Color.BLACK);
			      headBrowSkinTwo.setStrokeWidth(2.0);
			      return headBrowSkinTwo;  
		   }
		   public Node headBrowSkinThree() {
			   Polygon headBrowSkinThree = new Polygon();
			   headBrowSkinThree.getPoints().addAll(new Double[]{ 
						804.0,272.0,
						803.0,272.0,
						802.0,272.0,
						801.0,273.0,
						800.0,274.0,
						800.0,275.0,
						800.0,276.0,
						801.0,277.0,
						827.0,291.0,
						828.0,291.0,
						829.0,290.0,
						829.0,289.0,
						829.0,288.0,
						828.0,287.0,
						      });
		      headBrowSkinThree.setFill(Color.rgb(255, 71, 26));
		      headBrowSkinThree.setStroke(Color.BLACK);
		      headBrowSkinThree.setStrokeWidth(2.0);
		      return headBrowSkinThree;
		   }
		   public Node headBrowSkinFour() {
			   Polygon headBrowSkinFour = new Polygon();
			   headBrowSkinFour.getPoints().addAll(new Double[]{ 
						829.0,334.0,
						831.0,334.0,
						832.0,335.0,
						832.0,337.0,
						832.0,338.0,
						814.0,351.0,
						812.0,352.0,
						810.0,352.0,
						809.0,351.0,
						808.0,350.0,
						808.0,348.0,
						808.0,347.0,
						809.0,346.0,
						810.0,345.0,
						      });
		      headBrowSkinFour.setFill(Color.rgb(255, 71, 26));
		      headBrowSkinFour.setStroke(Color.BLACK);
		      headBrowSkinFour.setStrokeWidth(2.0);
		      return headBrowSkinFour;  
		   }
		   public Node headBrowSkinFive() {
			   Polygon headBrowSkinFive = new Polygon();
			   headBrowSkinFive.getPoints().addAll(new Double[]{ 
						840.0,345.0,
						841.0,344.0,
						843.0,343.0,
						844.0,343.0,
						845.0,344.0,
						845.0,345.0,
						845.0,346.0,
						844.0,348.0,
						823.0,387.0,
						822.0,386.0,
						821.0,384.0,
						820.0,383.0,
						819.0,381.0,
						819.0,380.0,
						820.0,378.0,
						
							      });
			      headBrowSkinFive.setFill(Color.rgb(255, 71, 26));
			      headBrowSkinFive.setStroke(Color.BLACK);
			      headBrowSkinFive.setStrokeWidth(2.0);
			      return headBrowSkinFive;
		   }
		   public Node headBrowSkinSix() {
			   Polygon headBrowSkinSix = new Polygon();
			   headBrowSkinSix.getPoints().addAll(new Double[]{ 
						855.0,348.0,
						856.0,348.0,
						857.0,348.0,
						858.0,348.0,
						859.0,349.0,
						859.0,350.0,
						859.0,351.0,
						859.0,352.0,
						846.0,391.0,
						844.0,393.0,
						843.0,394.0,
						841.0,394.0,
						839.0,394.0,
						838.0,393.0,
						838.0,391.0,
						839.0,390.0,
						839.0,389.0,
						839.0,388.0,
						
						
							      });
			      headBrowSkinSix.setFill(Color.rgb(255, 71, 26));
			      headBrowSkinSix.setStroke(Color.BLACK);
			      headBrowSkinSix.setStrokeWidth(2.0);
			      return headBrowSkinSix;
		   }
		   public Node rightBigAngleOne() {
			   Polygon rightBigAngleOne = new Polygon();
			   rightBigAngleOne.getPoints().addAll(new Double[]{ 
						878.0,364.0,
						902.0,411.0,
						1072.0,332.0,
						1104.0,342.0,
						1277.0,123.0,
						1079.0,295.0,
							      });
			   Light.Distant light = new Light.Distant(); 
			      
			      //Setting the properties of the light source 
			      light.setAzimuth(45.0); 
			      light.setElevation(30.0);       
			       
			      //Instantiating the Lighting class  
			      Lighting lighting = new Lighting(); 
			      
			      //Setting the source of the light 
			      lighting.setLight(light);
			  rightBigAngleOne.setEffect(lighting);
		      rightBigAngleOne.setFill(Color.YELLOW);
		      rightBigAngleOne.setStroke(Color.BLACK);
		      rightBigAngleOne.setStrokeWidth(2.0);
		      return rightBigAngleOne;
			   
		   }
		   public Node rightBigAngleTwo() {
			   Polygon rightBigAngleTwo = new Polygon();
			   rightBigAngleTwo.getPoints().addAll(new Double[]{ 
						878.0,364.0,
						1079.0,296.0,
						1277.0,123.0,
						1074.0,260.0,
						981.0,290.0,
						921.0,329.0,
						912.0,313.0,
						898.0,318.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.GOLD),  
				         new Stop(1, Color.WHITE)
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 0, 1, 0, true, CycleMethod.NO_CYCLE, stops); 
		      rightBigAngleTwo.setFill(linearGradient);
		      rightBigAngleTwo.setStroke(Color.BLACK);
		      rightBigAngleTwo.setStrokeWidth(2.0);
		      return rightBigAngleTwo;
			   
		   }
		   public Node rightSecondAngleOne() {
			   Polygon rightSecondAngleOne = new Polygon();
			   rightSecondAngleOne.getPoints().addAll(new Double[]{ 
						981.0,290.0,
						921.0,329.0,
						1002.0,102.0,
						1082.0,34.0,
						968.0,280.0,
							      });
			   Light.Distant light = new Light.Distant(); 
			      
			      //Setting the properties of the light source 
			      light.setAzimuth(45.0); 
			      light.setElevation(30.0);       
			       
			      //Instantiating the Lighting class  
			      Lighting lighting = new Lighting(); 
			      
			      //Setting the source of the light 
			      lighting.setLight(light);
			  rightSecondAngleOne.setEffect(lighting); 
		      rightSecondAngleOne.setFill(Color.YELLOW);
		      rightSecondAngleOne.setStroke(Color.BLACK);
		      rightSecondAngleOne.setStrokeWidth(2.0);
		      return rightSecondAngleOne;
			   
		   }
		   public Node rightSecondAngleTwo() {
			   Polygon rightSecondAngleTwo = new Polygon();
			   rightSecondAngleTwo.getPoints().addAll(new Double[]{ 
						1082.0,34.0,
						1002.0,102.0,
						923.0,137.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.GOLD),  
				         new Stop(1, Color.WHITE)
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 0, 1, 0, true, CycleMethod.NO_CYCLE, stops);  
		      rightSecondAngleTwo.setFill(linearGradient);
		      rightSecondAngleTwo.setStroke(Color.BLACK);
		      rightSecondAngleTwo.setStrokeWidth(2.0);
		      return rightSecondAngleTwo;
		      
		   }
		   public Node rightSecondAngleThree() {
			   Polygon rightSecondAngleThree = new Polygon();
			   rightSecondAngleThree.getPoints().addAll(new Double[]{ 
						923.0,137.0,
						1002.0,102.0,
						921.0,329.0,
						912.0,313.0,
						969.0,125.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.GOLD),  
				         new Stop(1, Color.WHITE)
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 0, 1, 0, true, CycleMethod.NO_CYCLE, stops); 
		      rightSecondAngleThree.setFill(linearGradient);
		      rightSecondAngleThree.setStroke(Color.BLACK);
		      rightSecondAngleThree.setStrokeWidth(2.0);
		      return rightSecondAngleThree;
		   }
		   public Node smallSizeHead() {
			   Polygon smallSizeHead = new Polygon();
			   smallSizeHead.getPoints().addAll(new Double[]{ 
						920.0,180.0,
						933.0,217.0,
						924.0,235.0,
						928.0,262.0,
						952.0,180.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      smallSizeHead.setFill(linearGradient);
		      smallSizeHead.setStroke(Color.BLACK);
		      smallSizeHead.setStrokeWidth(2.0);
		      return smallSizeHead;
			   
		   }
		   public Node sideHeadOne() {
			   Polygon sideHeadOne = new Polygon();
			   sideHeadOne.getPoints().addAll(new Double[]{ 
						1013.0,185.0,
						1015.0,186.0,
						1017.0,187.0,
						1019.0,188.0,
						1021.0,189.0,
						1023.0,190.0,
						1025.0,191.0,
						1027.0,192.0,
						1029.0,193.0,
						1031.0,194.0,
						1033.0,195.0,
						1035.0,196.0,
						1037.0,197.0,
						1039.0,198.0,
						1041.0,199.0,
						1043.0,200.0,
						1045.0,201.0,
						1047.0,202.0,
						1049.0,203.0,
						1051.0,204.0,
						1053.0,205.0,
						1055.0,206.0,
						1057.0,207.0,
						1059.0,208.0,
						1061.0,209.0,
						1063.0,210.0,
						1065.0,211.0,
						1067.0,212.0,
						1069.0,213.0,
						1071.0,214.0,
						1073.0,216.0,
						1075.0,217.0,
						1077.0,218.0,
						1079.0,219.0,
						1080.0,221.0,
						1082.0,222.0,
						1084.0,223.0,
						1086.0,225.0,
						1088.0,227.0,
						1090.0,229.0,
						1092.0,231.0,
						1094.0,233.0,
						1096.0,235.0,
						1098.0,237.0,
						1100.0,239.0,
						1103.0,240.0,
						1074.0,260.0,
						981.0,290.0,
						968.0,280.0,
							      });
		    
		   
				   Stop[] stops = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient = 
					         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      sideHeadOne.setFill(linearGradient);
		      sideHeadOne.setStroke(Color.BLACK);
		      sideHeadOne.setStrokeWidth(2.0);
		      return sideHeadOne;
		   }
		   public Node sideHeadLine() {
			   Polygon sideHeadLine = new Polygon();
			   sideHeadLine.getPoints().addAll(new Double[]{ 
						987.0,242.0,
						991.0,239.0,
						993.0,239.0,
						995.0,239.0,
						997.0,237.0,
						999.0,236.0,
						1001.0,236.0,
						1003.0,235.0,
						1005.0,235.0,
						1007.0,234.0,
						1009.0,235.0,
						1011.0,235.0,
						1013.0,235.0,
						1015.0,235.0,
						1017.0,235.0,
						1019.0,235.0,
						1021.0,235.0,
						1023.0,235.0,
						1025.0,235.0,
						1027.0,235.0,
						1029.0,235.0,
						1031.0,236.0,
						1033.0,237.0,
						1035.0,237.0,
						1037.0,238.0,
						1039.0,238.0,
						1041.0,239.0,
						1043.0,239.0,
						1045.0,240.0,
						1047.0,241.0,
						1049.0,241.0,
						1051.0,242.0,
						1053.0,243.0,
						1055.0,244.0,
						1057.0,245.0,
						1059.0,246.0,
						1061.0,247.0,
						1063.0,248.0,
						1065.0,249.0,
						1067.0,250.0,
						1069.0,251.0,
						1071.0,253.0,
						1073.0,254.0,
						1074.0,256.0,
						1076.0,257.0,
						1077.0,258.0,
						1074.0,260.0,
						981.0,290.0,
						968.0,280.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);   
		      sideHeadLine.setFill(linearGradient);
		      sideHeadLine.setStroke(Color.BLACK);
		      sideHeadLine.setStrokeWidth(2.0);
		      return sideHeadLine;
			   
		   }
		   public Node behindHeadLine() {
			   Polygon behindHeadLine = new Polygon();
			   behindHeadLine.getPoints().addAll(new Double[]{ 
						1142.0,294.0,///
						1134.0,343.0,///
						1126.0,314.0,//
								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 	
			      behindHeadLine.setFill(linearGradient);
			      behindHeadLine.setStroke(Color.BLACK);
			      behindHeadLine.setStrokeWidth(2.0);
			      return behindHeadLine;
		   }
		   public Node faceHeadHelmetOne() {
			   Polygon faceHeadHelmetOne = new Polygon();
			   faceHeadHelmetOne.getPoints().addAll(new Double[]{ 
						1126.0,314.0,
						1127.0,317.0,
						1129.0,320.0,
						1130.0,323.0,
						1130.0,325.0,
						1135.0,356.0,
						1132.0,356.0,
						1127.0,360.0,
						1125.0,361.0,
						1123.0,362.0,
						1121.0,363.0,
						1119.0,365.0,
						1118.0,367.0,
						1116.0,369.0,
						1114.0,372.0,
						1112.0,373.0,
						1111.0,376.0,
						1109.0,377.0,
						1108.0,379.0,
						1107.0,381.0,
						1106.0,383.0,
						1105.0,385.0,
						1104.0,387.0,
						1103.0,389.0,
						1102.0,391.0,
						1101.0,393.0,
						1100.0,396.0,
						1099.0,398.0,
						1098.0,400.0,
						1097.0,402.0,
						1096.0,404.0,
						1095.0,406.0,
						1094.0,408.0,
						1093.0,410.0,
						1092.0,413.0,
						1091.0,415.0,
						1090.0,417.0,
						1089.0,420.0,
						1086.0,421.0,
						1048.0,445.0,
						1048.0,378.0,
						906.0,410.0,
						1072.0,332.0,
						1104.0,342.0,
								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   
		      faceHeadHelmetOne.setFill(linearGradient);
		      faceHeadHelmetOne.setStroke(Color.BLACK);
		      faceHeadHelmetOne.setStrokeWidth(2.0);
		      return faceHeadHelmetOne;
		   }
		   public Node faceHeadHelmetTwo() {
			   Polygon faceHeadHelmetTwo = new Polygon();
			   faceHeadHelmetTwo.getPoints().addAll(new Double[]{ 
						1048.0,446.0,
						1034.0,446.0,
						1034.0,381.0,
						1048.0,378.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      faceHeadHelmetTwo.setFill(linearGradient);
		      faceHeadHelmetTwo.setStroke(Color.BLACK);
		      faceHeadHelmetTwo.setStrokeWidth(2.0);
		      return faceHeadHelmetTwo;
		   }
		   public Node eyelashDown() {
			   Polygon eyelashDown = new Polygon();
			   eyelashDown.getPoints().addAll(new Double[]{ 
						1033.0,445.0,
						1032.0,440.0,
						1029.0,438.0,
						963.0,479.0,
						899.0,467.0,
						892.0,476.0,
						955.0,490.0,
						957.0,488.0,
						959.0,486.0,
						961.0,485.0,
						963.0,484.0,
						
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);    
		      eyelashDown.setFill(linearGradient);
		      eyelashDown.setStroke(Color.BLACK);
		      eyelashDown.setStrokeWidth(2.0);
		      return eyelashDown;
		   }
		   public Node eyeLashDownTwo() {
			   Polygon eyeLashDownTwo = new Polygon();
			   eyeLashDownTwo.getPoints().addAll(new Double[]{ 
						899.0,467.0,
						892.0,476.0,
						883.0,473.0,
						891.0,460.0,
						
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);   
		      eyeLashDownTwo.setFill(linearGradient);
		      eyeLashDownTwo.setStroke(Color.BLACK);
		      eyeLashDownTwo.setStrokeWidth(2.0);
		      return eyeLashDownTwo;
		   }
		   public Node nose() {
			   Polygon nose = new Polygon(); 
			   nose.getPoints().addAll(new Double[]{ 
						883.0,473.0,
						865.0,474.0,
						878.0,460.0,
						891.0,460.0,
						
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      nose.setFill(linearGradient);
		      nose.setStroke(Color.BLACK);
		      nose.setStrokeWidth(2.0);
		      return nose;
		   }
		   public Node eyeLashDownThree() {
			   Polygon eyeLashDownThree = new Polygon();
			   eyeLashDownThree.getPoints().addAll(new Double[]{ 
						865.0,474.0,
						840.0,490.0,
						831.0,473.0,
						832.0,462.0,
						842.0,479.0,
						872.0,467.0,
						
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      eyeLashDownThree.setFill(linearGradient);
		      eyeLashDownThree.setStroke(Color.BLACK);
		      eyeLashDownThree.setStrokeWidth(2.0);
		      return eyeLashDownThree;
		   }
		   public Node blackSkinFace() {
			   Polygon blackSkinFace = new Polygon();
			   blackSkinFace.getPoints().addAll(new Double[]{ 
						1034.0,443.0,
						1032.0,440.0,
						1029.0,438.0,
						963.0,479.0,
						899.0,467.0,
						891.0,460.0,
						878.0,460.0,
						872.0,467.0,
						842.0,479.0,
						832.0,462.0,
						831.0,473.0,//
						831.0,483.0,
						833.0,485.0,
						833.0,489.0,
						835.0,493.0,
						836.0,496.0,
						836.0,499.0,
						837.0,501.0,
						838.0,504.0,
						839.0,508.0,
						840.0,512.0,
						841.0,516.0,
						842.0,519.0,
						843.0,522.0,
						844.0,524.0,
						845.0,527.0,
						846.0,530.0,
						847.0,533.0,
						848.0,536.0,
						850.0,538.0,
						851.0,541.0,
						852.0,544.0,
						854.0,547.0,
						856.0,550.0,
						858.0,552.0,
						859.0,554.0,
						861.0,556.0,
						862.0,558.0,//
						851.0,558.0,
						847.0,577.0,
						844.0,577.0,
						839.0,587.0,
						838.0,581.0,
						827.0,581.0,
						825.0,584.0,
						823.0,584.0,//end
						812.0,546.0,
						808.0,485.0,
						808.0,484.0,
						822.0,445.0, //
						820.0,428.0,//
						820.0,410.0,///
						833.0,428.0,
						833.0,442.0,
						834.0,445.0,
						835.0,451.0,
						836.0,455.0,
						837.0,456.0,
						838.0,458.0,
						839.0,460.0,
						840.0,462.0,
						841.0,464.0,
						842.0,466.0,
						843.0,469.0,
						845.0,472.0,
						848.0,472.0,
						850.0,472.0,
						852.0,471.0,
						854.0,470.0,
						856.0,469.0,
						859.0,468.0,
						861.0,467.0,
						863.0,466.0,
						865.0,465.0,
						867.0,464.0,
						869.0,463.0,
						871.0,462.0,
						873.0,461.0,
						874.0,459.0,
						875.0,457.0,
						876.0,455.0,
						877.0,453.0,
						878.0,451.0,
						879.0,449.0,
						879.0,446.0,
						880.0,444.0,
						880.0,442.0,
						880.0,441.0,
						//879.0,440.0,
						//879.0,439.0,
						906.0,410.0,
						914.0,410.0,
						914.0,412.0,
						913.0,414.0,
						912.0,416.0,
						911.0,418.0,
						910.0,420.0,
						909.0,422.0,
						908.0,424.0,
						907.0,425.0,
						906.0,427.0,
						906.0,429.0,
						905.0,431.0,
						904.0,434.0,
						902.0,435.0,
						902.0,445.0,
						903.0,441.0,
						904.0,451.0,
						905.0,453.0,
						906.0,455.0,
						907.0,458.0,
						909.0,461.0,
						911.0,463.0,
						913.0,464.0,
						//916.0,465.0,
						//924.0,465.0,
						//927.0,466.0,
						931.0,467.0,
						935.0,468.0,
						939.0,469.0,
						945.0,470.0,
						952.0,471.0,
						963.0,473.0,
						1022.0,435.0,
						1026.0,411.0,
						1017.0,387.0,
						1034.0,382.0,
						
						
						
						
							      });
		      blackSkinFace.setFill(Color.BLACK);
		      blackSkinFace.setStroke(Color.BLACK);
		      blackSkinFace.setStrokeWidth(2.0);
		      return blackSkinFace;
		   }
		   public Node eyeBallOne() {
			   Polygon eyeBallOne = new Polygon();
			   eyeBallOne.getPoints().addAll(new Double[]{ 
			    		  833.0,428.0,
							833.0,442.0,
							834.0,445.0,
							835.0,451.0,
							836.0,455.0,
							837.0,456.0,
							838.0,458.0,
							839.0,460.0,
							840.0,462.0,
							841.0,464.0,
							842.0,466.0,
							843.0,469.0,
							845.0,472.0,
							848.0,472.0,
							850.0,472.0,
							852.0,471.0,
							854.0,470.0,
							856.0,469.0,
							859.0,468.0,
							861.0,467.0,
							863.0,466.0,
							865.0,465.0,
							867.0,464.0,
							869.0,463.0,
							871.0,462.0,
							873.0,461.0,
							874.0,459.0,
							875.0,457.0,
							876.0,455.0,
							877.0,453.0,
							878.0,451.0,
							879.0,449.0,
							879.0,446.0,
							880.0,444.0,
							880.0,442.0,
							880.0,441.0,
							878.0,442.0,
							844.0,442.0,
							
								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.GOLD),  
				         new Stop(1, Color.LIGHTYELLOW)
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 0, 1, 0, true, CycleMethod.NO_CYCLE, stops); 	
			     eyeBallOne.setFill(linearGradient);
			     return eyeBallOne;
			   
		   }
		   public Node eyeBallTwo() {
			   Polygon eyeBallTwo = new Polygon();
			   eyeBallTwo.getPoints().addAll(new Double[]{ 
			    		  914.0,410.0,
							914.0,412.0,
							913.0,414.0,
							912.0,416.0,
							911.0,418.0,
							910.0,420.0,
							909.0,422.0,
							908.0,424.0,
							907.0,425.0,
							906.0,427.0,
							906.0,429.0,
							905.0,431.0,
							904.0,434.0,
							902.0,435.0,
							902.0,445.0,
							903.0,441.0,
							904.0,451.0,
							905.0,453.0,
							906.0,455.0,
							907.0,458.0,
							909.0,461.0,
							911.0,463.0,
							913.0,464.0,
							931.0,467.0,
							935.0,468.0,
							939.0,469.0,
							945.0,470.0,
							952.0,471.0,
							963.0,473.0,
							1022.0,435.0,
							1026.0,411.0,
							1017.0,387.0,
							
								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.GOLD),  
				         new Stop(1, Color.LIGHTYELLOW)
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 0, 1, 0, true, CycleMethod.NO_CYCLE, stops); 
			      eyeBallTwo.setFill(linearGradient);
			      return eyeBallTwo;
		   }
		   public Node helmetSkinRight() {
			   Polygon helmetSkinRight = new Polygon();
			   helmetSkinRight.getPoints().addAll(new Double[]{ 
						1149.0,466.0,
						1150.0,464.0,
						1151.0,462.0,
						1152.0,460.0,
						1153.0,458.0,
						1154.0,451.0,
						1154.0,406.0,
						1153.0,397.0,
						1152.0,392.0,
						1151.0,388.0,
						1150.0,382.0,
						1148.0,376.0,
						1147.0,373.0,
						1146.0,372.0,
						1144.0,368.0,
						1143.0,366.0,
						1142.0,364.0,
						1141.0,362.0,
						1139.0,360.0,
						1138.0,358.0,
						1136.0,357.0,
						1135.0,356.0,
						1132.0,356.0,
						1127.0,360.0,
						1125.0,361.0,
						1123.0,362.0,
						1121.0,363.0,
						1119.0,365.0,
						1118.0,367.0,
						1116.0,369.0,
						1114.0,372.0,
						1112.0,373.0,
						1111.0,376.0,
						1109.0,377.0,
						1108.0,379.0,
						1107.0,381.0,
						1106.0,383.0,
						1105.0,385.0,
						1104.0,387.0,
						1103.0,389.0,
						1102.0,391.0,
						1101.0,393.0,
						1100.0,396.0,
						1099.0,398.0,
						1098.0,400.0,
						1097.0,402.0,
						1096.0,404.0,
						1095.0,406.0,
						1094.0,408.0,
						1093.0,410.0,
						1092.0,413.0,
						1091.0,415.0,
						1090.0,417.0,
						1089.0,420.0,
						1086.0,421.0,
						1048.0,445.0,
						1048.0,446.0,
						1034.0,446.0,
						1033.0,445.0,
						963.0,484.0,
						961.0,485.0,
						959.0,486.0,
						957.0,488.0,
						955.0,490.0,
						955.0,547.0,
						954.0,551.0,
						953.0,554.0,
						952.0,557.0,
						951.0,560.0,
						950.0,566.0,
						949.0,567.0,
						948.0,571.0,
						947.0,575.0,
						946.0,579.0,
						945.0,581.0,
						944.0,582.0,
						979.0,579.0,
						1018.0,569.0,
						1022.0,569.0,
						1028.0,568.0,
						1030.0,566.0,
						1033.0,565.0,
						1037.0,564.0,
						1039.0,563.0,
						1041.0,562.0,
						1043.0,561.0,
						1045.0,560.0,
						1058.0,541.0,
						1066.0,541.0,
						1066.0,537.0,
						1061.0,536.0,
						1053.0,531.0,
						1052.0,513.0,
						1060.0,503.0,
						1073.0,501.0,
						1082.0,476.0,
						1084.0,476.0,
						1084.0,450.0,
						1082.0,450.0,
						1082.0,448.0,
						1089.0,438.0,
						1127.0,438.0,/////
						1130.0,441.0,
						1132.0,446.0,
						1133.0,451.0,
						1134.0,453.0,
						1134.0,462.0,
						1133.0,465.0,
						1133.0,467.0,

							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops);   
		      helmetSkinRight.setFill(linearGradient);
		      helmetSkinRight.setStroke(Color.BLACK);
		      helmetSkinRight.setStrokeWidth(2.0);
		      return helmetSkinRight;
			   
			   
		   }
		   public Node monthOne() {
			   Polygon monthOne = new Polygon();
			   monthOne.getPoints().addAll(new Double[]{ 
						955.0,490.0,
						892.0,476.0,
						883.0,473.0,
						865.0,474.0,
						840.0,490.0,
						831.0,473.0,
						831.0,483.0,
						833.0,485.0,
						833.0,489.0,
						835.0,493.0,
						836.0,496.0,
						836.0,499.0,
						837.0,501.0,
						838.0,504.0,
						839.0,508.0,
						840.0,512.0,
						841.0,516.0,
						842.0,519.0,
						843.0,522.0,
						844.0,524.0,
						845.0,527.0,
						846.0,530.0,
						847.0,533.0,
						848.0,536.0,
						850.0,538.0,
						851.0,541.0,
						852.0,544.0,
						854.0,547.0,
						856.0,550.0,
						858.0,552.0,
						859.0,554.0,
						861.0,556.0,
						862.0,558.0,
						866.0,562.0,
						872.0,579.0,
						873.0,580.0,
						905.0,580.0,
						927.0,562.0,
						930.0,561.0,
						932.0,560.0,
						934.0,559.0,
						936.0,558.0,
						938.0,557.0,
						940.0,556.0,
						942.0,555.0,
						943.0,554.0,
						945.0,553.0,
						947.0,551.0,
						949.0,549.0,
						951.0,547.0,
						953.0,545.0,
						955.0,544.0,
							      });
		      monthOne.setFill(Color.WHITE);
		      monthOne.setStroke(Color.BLACK);
		      monthOne.setStrokeWidth(2.0);
		      return monthOne;
		   }
		   public Node monthTwo() {
			   Polygon monthTwo = new Polygon();
			   monthTwo.getPoints().addAll(new Double[]{ 
						955.0,490.0,
						892.0,476.0,
						883.0,473.0,
						865.0,474.0,
						840.0,490.0,
						840.0,493.0,
						840.0,496.0,
						841.0,499.0,
						842.0,503.0,
						843.0,506.0,
						844.0,510.0,
						845.0,512.0,
						846.0,517.0,
						847.0,521.0,
						848.0,523.0,
						849.0,527.0,
						850.0,529.0,
						851.0,532.0,
						852.0,534.0,
						853.0,536.0,
						854.0,538.0,
						862.0,546.0,
						873.0,517.0,
						891.0,517.0,
						917.0,548.0,
						920.0,547.0,
						922.0,546.0,
						924.0,545.0,
						926.0,544.0,
						928.0,543.0,
						930.0,542.0,
						932.0,540.0,
						934.0,539.0,
						936.0,537.0,
						938.0,535.0,
						940.0,533.0,
						941.0,530.0,
						943.0,528.0,
						944.0,526.0,
						945.0,524.0,
						946.0,521.0,
						947.0,518.0,
						948.0,517.0,
						949.0,514.0,
						950.0,512.0,
						951.0,510.0,
						952.0,507.0,
						953.0,505.0,
						954.0,502.0,
						955.0,499.0,
						
							      });
		      monthTwo.setFill(Color.WHITE);
		      monthTwo.setStroke(Color.BLACK);
		      monthTwo.setStrokeWidth(2.0);
		      return monthTwo;
		   }
		   public Node faceHeadHelmetThree() {
			      Polygon faceHeadHelmetThree = new Polygon();
			      faceHeadHelmetThree.getPoints().addAll(new Double[]{ 
							820.0,410.0,
							820.0,428.0,
							822.0,445.0,
							808.0,484.0,
							808.0,485.0,
							812.0,546.0,
							823.0,584.0,
							821.0,582.0,
							820.0,581.0,
							819.0,580.0,
							818.0,579.0,
							817.0,578.0,
							816.0,577.0,
							815.0,576.0,
							814.0,575.0,
							813.0,574.0,
							812.0,573.0,
							811.0,571.0,
							810.0,570.0,
							809.0,568.0,
							808.0,566.0,
							806.0,564.0,
							805.0,562.0,
							803.0,560.0,
							802.0,558.0,
							801.0,556.0,
							799.0,554.0,
							798.0,552.0,
							797.0,550.0,
							796.0,547.0,
							795.0,542.0,
							794.0,541.0,
							793.0,533.0,
							792.0,532.0,
							792.0,499.0,
							793.0,483.0,
							795.0,461.0,
							795.0,442.0,
							798.0,401.0,
							793.0,396.0,
							792.0,394.0,
							793.0,392.0,
							795.0,391.0,
							796.0,391.0,
							
								      });
			      Stop[] stops = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient = 
					         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
			      faceHeadHelmetThree.setFill(linearGradient);
			      faceHeadHelmetThree.setStroke(Color.BLACK);
			      faceHeadHelmetThree.setStrokeWidth(2.0);
			      return faceHeadHelmetThree;
			   
		   }
		   public Node chinOne() {
			   Polygon chinOne = new Polygon();
			   chinOne.getPoints().addAll(new Double[]{ 
						927.0,562.0,
						891.0,518.0,
						885.0,545.0,
						884.0,551.0,
						905.0,580.0,
						
						
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      chinOne.setFill(linearGradient);
		      chinOne.setStroke(Color.BLACK);
		      chinOne.setStrokeWidth(2.0);
		      return chinOne;
		   }
		   public Node chinTwo() {
			   Polygon chinTwo = new Polygon();
			   chinTwo.getPoints().addAll(new Double[]{ 
						891.0,517.0,
						873.0,517.0,
						862.0,546.0,
						//863.0,548.0,
						862.0,550.0,
						863.0,551.0,
						884.0,551.0,
						
						
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      chinTwo.setFill(linearGradient);
		      chinTwo.setStroke(Color.BLACK);
		      chinTwo.setStrokeWidth(2.0);
		      return chinTwo;
		   }
		   public Node chinThree() {
			   Polygon chinThree = new Polygon();
			   
			      chinThree.getPoints().addAll(new Double[]{ 
						873.0,580.0,
						905.0,580.0,
						884.0,551.0,
						863.0,551.0,
						
								      });
			      Stop[] stops = new Stop[] { 
					         new Stop(0, Color.rgb(255, 71, 26)),  
					         new Stop(1, Color.DARKRED),
					         
					      };  
					      LinearGradient linearGradient = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);  
			      chinThree.setFill(linearGradient);
			      chinThree.setStroke(Color.BLACK);
			      chinThree.setStrokeWidth(2.0);
			      return chinThree;     
		   }
		   public Node mouthThree() {
			   Polygon mouthThree = new Polygon();
			   mouthThree.getPoints().addAll(new Double[]{ 
						892.0,492.0,
						894.0,492.0,
						896.0,492.0,
						896.0,489.0,
						886.0,484.0,
						864.0,484.0,
						859.0,489.0,
						858.0,491.0,
						861.0,492.0,
						866.0,488.0,
						884.0,488.0,
						
								      });
		      mouthThree.setFill(Color.BLACK);
		      mouthThree.setStroke(Color.BLACK);
			  mouthThree.setStrokeWidth(2.0);
			  return mouthThree;
		   }
		   public Node mouthFour() {
			   Polygon mouthFour = new Polygon();
			   mouthFour.getPoints().addAll(new Double[]{ 
						894.0,503.0,
						896.0,503.0,
						898.0,503.0,
						898.0,499.0,
						888.0,494.0,
						867.0,494.0,
						861.0,499.0,
						861.0,500.0,
						861.0,502.0,
						864.0,502.0,
						868.0,499.0,
						887.0,499.0,
								      });
		      mouthFour.setFill(Color.BLACK);
		      mouthFour.setStroke(Color.BLACK);
		      mouthFour.setStrokeWidth(2.0);
		      return mouthFour;
		   }
		   public Node faceHeadHelmetFour() {
			   Polygon faceHeadHelmetFour = new Polygon();
			   faceHeadHelmetFour.getPoints().addAll(new Double[]{ 
						795.0,391.0,
						793.0,392.0,
						792.0,394.0,
						793.0,396.0,
						798.0,401.0,
						808.0,407.0,
						820.0,410.0,
						813.0,403.0,
								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops);   
		      faceHeadHelmetFour.setFill(linearGradient);
		      faceHeadHelmetFour.setStroke(Color.BLACK);
		      faceHeadHelmetFour.setStrokeWidth(2.0);
		      return faceHeadHelmetFour;
		   }
		   public Node faceHeadHelmetFive() {
			   Polygon faceHeadHelmetFive = new Polygon();
			   
			      faceHeadHelmetFive.getPoints().addAll(new Double[]{ 
							808.0,407.0,
							820.0,411.0,
							822.0,445.0,
							808.0,445.0,
									      });
			      Stop[] stops = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient = 
					         new LinearGradient(1,0, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
			      
			      faceHeadHelmetFive.setFill(linearGradient);
			      faceHeadHelmetFive.setStroke(Color.BLACK);
			      faceHeadHelmetFive.setStrokeWidth(2.0);
			      return faceHeadHelmetFive;
		   }
		   public Node leftVentOne() {
			   Polygon leftVentOne = new Polygon();
			   leftVentOne.getPoints().addAll(new Double[]{ 
						804.0,490.0,
						803.0,490.0,
						802.0,490.0,
						795.0,498.0,
						796.0,532.0,
						797.0,537.0,
						798.0,542.0,
						799.0,548.0,
						815.0,571.0,
						816.0,570.0,
						815.0,568.0,
						815.0,566.0,
						814.0,564.0,
						813.0,562.0,
						813.0,559.0,
						813.0,557.0,
						811.0,555.0,
						811.0,552.0,
						810.0,550.0,
						809.0,547.0,
								      });
		      leftVentOne.setFill(Color.BLACK);
		      leftVentOne.setStroke(Color.BLACK);
		      leftVentOne.setStrokeWidth(2.0);
		      return leftVentOne;
			   
		   }
		   public Node leftVentTwo() {
			   Polygon leftVentTwo = new Polygon();
			      leftVentTwo.getPoints().addAll(new Double[]{ 
							798.0,511.0,
							797.0,512.0,
							797.0,513.0,
							798.0,514.0,
							803.0,514.0,
							804.0,513.0,
							804.0,512.0,
							803.0,511.0,
									      });
			      Stop[] stops = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient = 
					         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
			        
			      leftVentTwo.setFill(linearGradient);
			      return leftVentTwo; 
			  
		   }
		   public Node leftVentThree() {
			   Polygon leftVentThree = new Polygon();
			   leftVentThree.getPoints().addAll(new Double[]{ 
						799.0,531.0,
						798.0,532.0,
						798.0,533.0,
						798.0,534.0,
						800.0,536.0,
						805.0,536.0,
						806.0,535.0,
						806.0,534.0,
						806.0,533.0,
						806.0,532.0,
						805.0,531.0,
								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      leftVentThree.setFill(linearGradient);
		     return leftVentThree;
		      
		   }
		   public Node leftVentFour() {
			   Polygon leftVentFour = new Polygon();
			   leftVentFour.getPoints().addAll(new Double[]{ 
						803.0,549.0,
						802.0,550.0,
						802.0,551.0,
						803.0,552.0,
						804.0,553.0,
						807.0,553.0,
						808.0,552.0,
						808.0,551.0,
						807.0,549.0,
								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      leftVentFour.setFill(linearGradient);
		      return leftVentFour;
		      
			   
		   }
		   public Node headEyeTwo() {
			   Polygon headEyeTwo = new Polygon();
			   headEyeTwo.getPoints().addAll(new Double[]{ 
						849.0,293.0,
						848.0,295.0,
						846.0,296.0,
						845.0,298.0,
						843.0,299.0,
						842.0,301.0,
						841.0,303.0,
						840.0,304.0,
						839.0,306.0,
						839.0,313.0,
						840.0,316.0,
						841.0,318.0,
						842.0,320.0,
						843.0,322.0,
						845.0,324.0,
						850.0,327.0,
						852.0,328.0,
						855.0,329.0,
						857.0,330.0,
						859.0,330.0,
						861.0,329.0,
						863.0,328.0,
						865.0,327.0,
						867.0,326.0,
						868.0,324.0,
						870.0,322.0,
						871.0,319.0,
						872.0,317.0,
						872.0,305.0,
						863.0,293.0,
							
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			      headEyeTwo.setFill(linearGradient);
			      headEyeTwo.setStroke(Color.BLACK);
			      headEyeTwo.setStrokeWidth(2.0);
			      return headEyeTwo;
		   }
		   public Node headEyeThree() {
			   Polygon headEyeThree = new Polygon();
			   headEyeThree.getPoints().addAll(new Double[]{ 
						854.0,298.0,
						853.0,299.0,
						851.0,300.0,
						851.0,302.0,
						849.0,304.0,
						848.0,306.0,
						847.0,308.0,
						847.0,312.0,
						848.0,314.0,
						848.0,317.0,
						851.0,321.0,
						854.0,323.0,
						858.0,324.0,
						862.0,324.0,
						864.0,323.0,
						866.0,322.0,
						868.0,320.0,
						869.0,318.0,
						870.0,316.0,
						870.0,306.0,
						865.0,300.0,
						863.0,299.0,
						862.0,298.0,
							      });
		      headEyeThree.setFill(Color.BLACK);
		      return headEyeThree;  
		   }
		   public Node rightVentOne() {
			   Polygon rightVentOne = new Polygon();
			   rightVentOne.getPoints().addAll(new Double[]{ 
						961.0,492.0,
						977.0,500.0,
						977.0,553.0,
						950.0,579.0,
						950.0,578.0,
						950.0,577.0,
						956.0,570.0,
						963.0,556.0,
						963.0,554.0,
						961.0,555.0,
						960.0,554.0,
						960.0,548.0,
						961.0,547.0,
						964.0,547.0,
						964.0,536.0,
						963.0,536.0,
						961.0,534.0,
						961.0,530.0,
						962.0,529.0,
						964.0,529.0,
						964.0,518.0,
						962.0,516.0,
						961.0,515.0,
						961.0,511.0,
						962.0,510.0,
						964.0,510.0,
						964.0,494.0,
							      });
		      rightVentOne.setFill(Color.BLACK);
		      return rightVentOne;
		   }
		   public Node rightVentTwo() {
			   Polygon rightVentTwo = new Polygon();
			   rightVentTwo.getPoints().addAll(new Double[]{ 
						964.0,510.0,
						962.0,510.0,
						961.0,515.0,
						962.0,516.0,
						964.0,518.0,
						975.0,518.0,
						975.0,510.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      rightVentTwo.setFill(linearGradient);
		      rightVentTwo.setStroke(Color.BLACK);
		      rightVentTwo.setStrokeWidth(2.0);
		      return rightVentTwo;
			   
		   }
		   public Node rightVentThree() {
			   Polygon rightVentThree = new Polygon();
			   rightVentThree.getPoints().addAll(new Double[]{ 
						964.0,529.0,
						962.0,529.0,
						961.0,530.0,
						961.0,534.0,
						963.0,536.0,
						964.0,536.0,
						975.0,536.0,
						975.0,529.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      rightVentThree.setFill(linearGradient);
		      rightVentThree.setStroke(Color.BLACK);
		      rightVentThree.setStrokeWidth(2.0);
		      return rightVentThree;
		   }
		   public Node rightVentFour() {
			   Polygon rightVentFour = new Polygon();
			   rightVentFour.getPoints().addAll(new Double[]{ 
						964.0,547.0,
						961.0,547.0,
						960.0,548.0,
						960.0,554.0,
						961.0,555.0,
						963.0,554.0,
						975.0,554.0,
						976.0,551.0,
						976.0,547.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      rightVentFour.setFill(linearGradient);
		      rightVentFour.setStroke(Color.BLACK);
		      rightVentFour.setStrokeWidth(2.0);
		      return rightVentFour; 
		   }
		   public Node rightShoulderOne() {
			   Polygon rightShoulderOne = new Polygon(); 
			   rightShoulderOne.getPoints().addAll(new Double[]{ 
						1133.0,467.0,
						1133.0,465.0,
						1134.0,462.0,
						1134.0,453.0,
						1133.0,451.0,
						1132.0,446.0,
						1130.0,441.0,
						1127.0,438.0,
						1089.0,438.0,
						1082.0,448.0,
						1082.0,450.0,
						1084.0,450.0,
						1084.0,476.0,
							      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      rightShoulderOne.setFill(linearGradient);
		      rightShoulderOne.setStroke(Color.BLACK);
		      rightShoulderOne.setStrokeWidth(2.0);
		      
		      Polygon rightShoulderTwo = new Polygon();
			   rightShoulderTwo.getPoints().addAll(new Double[]{ 
						1084.0,450.0,
						1097.0,452.0,
						1097.0,473.0,
						1084.0,476.0,
							      });
		      rightShoulderTwo.setFill(Color.BLACK);
		      
		      Polygon rightShoulderThree = new Polygon();
			   rightShoulderThree.getPoints().addAll(new Double[]{ 
						1082.0,476.0,
						1119.0,470.0,
						1123.0,493.0,
						1073.0,501.0,
							      });
			   Stop[] stopsThree = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradientThree = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stopsThree);   
		      rightShoulderThree.setFill(linearGradientThree);
		      rightShoulderThree.setStroke(Color.BLACK);
		      rightShoulderThree.setStrokeWidth(2.0);
		      
		      Polygon rightShoulderFour = new Polygon();
			   rightShoulderFour.getPoints().addAll(new Double[]{ 
						1119.0,470.0,
						1139.0,466.0,
						1147.0,490.0,
						1123.0,493.0,
						
							      });
			   Stop[] stopsFour = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradientFour = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stopsFour); 
		      rightShoulderFour.setFill(linearGradientFour);
		      rightShoulderFour.setStroke(Color.BLACK);
		      rightShoulderFour.setStrokeWidth(2.0);
		      
		      Polygon rightShoulderFive = new Polygon();
			   rightShoulderFive.getPoints().addAll(new Double[]{ 
						1139.0,466.0,
						1159.0,466.0,
						1167.0,486.0,
						1147.0,490.0,
							      });
			   Stop[] stopsFive = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradientFive = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stopsFive);  
		      rightShoulderFive.setFill(linearGradientFive);
		      rightShoulderFive.setStroke(Color.BLACK);
		      rightShoulderFive.setStrokeWidth(2.0);
		      
		      Polygon rightShoulderSix = new Polygon();
			   rightShoulderSix.getPoints().addAll(new Double[]{ 
						1147.0,490.0,
						1141.0,472.0,
						1151.0,472.0,
						1158.0,488.0,
								      });
			      rightShoulderSix.setFill(Color.BLACK);
			      
			      Polygon rightShoulderSeven = new Polygon();
				   
			      rightShoulderSeven.getPoints().addAll(new Double[]{ 
							1066.0,537.0,
							1061.0,536.0,
							1053.0,531.0,
							1052.0,513.0,
							1060.0,503.0,
							1073.0,501.0,
							1390.0,450.0,
							1314.0,503.0,
							1289.0,494.0,
								      });
			      Stop[] stopsSix = new Stop[] { 
					         new Stop(0, Color.rgb(255, 71, 26)),  
					         new Stop(1, Color.DARKRED),
					         
					      };  
					      LinearGradient linearGradientSix = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stopsSix);  
			      rightShoulderSeven.setFill(linearGradientSix);
			      rightShoulderSeven.setStroke(Color.BLACK);
			      rightShoulderSeven.setStrokeWidth(2.0);
			      
			      Polygon rightShoulderEight = new Polygon();
				   rightShoulderEight.getPoints().addAll(new Double[]{ 
							1390.0,450.0,
							1420.0,450.0,
							1420.0,451.0,
							1343.0,503.0,
							1314.0,503.0,
								      });
				   Stop[] stopsSeven = new Stop[] { 
					         new Stop(0, Color.rgb(255, 71, 26)),  
					         new Stop(1, Color.DARKRED),
					         
					      };  
					      LinearGradient linearGradientSeven = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stopsSeven);  
			      rightShoulderEight.setFill(linearGradientSeven);
			      rightShoulderEight.setStroke(Color.BLACK);
			      rightShoulderEight.setStrokeWidth(2.0);
			      
			      Polygon rightShoulderNine = new Polygon();
				   
			      rightShoulderNine.getPoints().addAll(new Double[]{ 
							1066.0,537.0,
							1289.0,494.0,
							1309.0,502.0,
							1205.0,529.0,
							1205.0,527.0,
							1205.0,525.0,
							1203.0,524.0,
							1191.0,524.0,
							1176.0,526.0,
							1169.0,524.0,
							1118.0,532.0,
							1100.0,536.0,
								      });
			      Stop[] stopsEight = new Stop[] { 
					         new Stop(0, Color.rgb(255, 71, 26)),  
					         new Stop(1, Color.DARKRED),
					         
					      };  
					      LinearGradient linearGradientEight = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stopsEight);  
			      rightShoulderNine.setFill(linearGradientEight);
			      rightShoulderNine.setStroke(Color.BLACK);
			      rightShoulderNine.setStrokeWidth(2.0);
			      
			      Polygon rightShoulderTen = new Polygon();
				   rightShoulderTen.getPoints().addAll(new Double[]{ 
							1383.0,456.0,
							1391.0,456.0,
							1392.0,457.0,
							1392.0,458.0,
							1338.0,495.0,
							1326.0,495.0,
								      });
			      rightShoulderTen.setFill(Color.BLACK);
			      
			      Polygon rightShoulder12 = new Polygon();
				   rightShoulder12.getPoints().addAll(new Double[]{ 
							1076.0,518.0,
							1076.0,517.0,
							1076.0,516.0,
							1080.0,511.0,
							1079.0,509.0,
							1077.0,507.0,
							1075.0,506.0,
							1068.0,506.0,
							1066.0,507.0,
							1064.0,509.0,
							1062.0,511.0,
							1060.0,513.0,
							1059.0,515.0,
							1058.0,517.0,
							1058.0,520.0,
							1059.0,523.0,
							1061.0,525.0,
							1063.0,527.0,
							1065.0,529.0,
							1067.0,530.0,
							1070.0,530.0,
							1074.0,530.0,
							1076.0,529.0,
							1077.0,527.0,
							1081.0,523.0,
							
								      });
				   Stop[] stopsNine = new Stop[] { 
					         new Stop(0, Color.rgb(255, 71, 26)),  
					         new Stop(1, Color.DARKRED),
					         
					      };  
					      LinearGradient linearGradientNine = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stopsNine); 
			      rightShoulder12.setFill(linearGradientNine);
			      rightShoulder12.setStroke(Color.BLACK);
			      rightShoulder12.setStrokeWidth(2.0);
			      
			      Polygon rightShoulder11 = new Polygon();
				   rightShoulder11.getPoints().addAll(new Double[]{ 
							1075.0,515.0,
							1075.0,516.0,
							1075.0,517.0,
							1075.0,518.0,
							1075.0,519.0,
							1074.0,521.0,
							1073.0,523.0,
							1072.0,524.0,
							1071.0,525.0,
							1070.0,525.0,
							1068.0,524.0,
							1065.0,522.0,
							1063.0,519.0,
							1063.0,517.0,
							1064.0,515.0,
							1066.0,512.0,
							1068.0,511.0,
							1071.0,511.0,
							1073.0,513.0,
								      });
				   
			      rightShoulder11.setFill(Color.BLACK);
			      rightShoulder11.setStroke(Color.BLACK);
			      rightShoulder11.setStrokeWidth(2.0);
			      
			      Polygon rightShoulder13 = new Polygon();
				   rightShoulder13.getPoints().addAll(new Double[]{ 
							1076.0,517.0,
							1081.0,523.0,
							1157.0,503.0,
							1081.0,510.0,
								      });
				   Stop[] stopsTen = new Stop[] { 
					         new Stop(0, Color.rgb(255, 71, 26)),  
					         new Stop(1, Color.DARKRED),
					         
					      };  
					      LinearGradient linearGradientTen = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stopsTen);  
			      rightShoulder13.setFill(linearGradientTen);
			      rightShoulder13.setStroke(Color.BLACK);
			      rightShoulder13.setStrokeWidth(2.0);
			      
			      Polygon rightShoulder14 = new Polygon();
				   rightShoulder14.getPoints().addAll(new Double[]{ 
							1058.0,541.0,
							1125.0,533.0,
							1144.0,533.0,
							1159.0,559.0,
							1125.0,658.0,
							1062.0,691.0,
							1048.0,668.0,
							1047.0,667.0,
							1045.0,561.0,
								      });
				   Stop[] stops11 = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient11 = 
					         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops11);    
			      rightShoulder14.setFill(linearGradient11);
			      rightShoulder14.setStroke(Color.BLACK);
			      rightShoulder14.setStrokeWidth(2.0);
			      
			      Polygon rightShoulder15 = new Polygon();
				   rightShoulder15.getPoints().addAll(new Double[]{ 
							1058.0,541.0,
							1125.0,533.0,
							1133.0,555.0,
							1134.0,559.0,
							1132.0,563.0,
							1108.0,635.0,
							1106.0,640.0,
							1103.0,642.0,
							1047.0,667.0,
							1045.0,561.0,
								      });
				   Stop[] stops12 = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient12 = 
					         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops12);    
			      rightShoulder15.setFill(linearGradient12);
			      rightShoulder15.setStroke(Color.BLACK);
			      rightShoulder15.setStrokeWidth(2.0);
			      
			      Polygon rightShoulder16 = new Polygon();
				   rightShoulder16.getPoints().addAll(new Double[]{ 
							1056.0,584.0,
							1058.0,581.0,
							1062.0,579.0,
							1106.0,576.0,
							1109.0,577.0,
							1111.0,581.0,
							1111.0,598.0,
							1109.0,601.0,
							1106.0,603.0,
							1063.0,607.0,
							1060.0,606.0,
							1058.0,604.0,
								      });
				   Stop[] stops13 = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient13 = 
					         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops13);  
			      rightShoulder16.setFill(linearGradient13);
			      rightShoulder16.setStroke(Color.BLACK);
			      rightShoulder16.setStrokeWidth(2.0);
			      
			      Polygon rightShoulder17 = new Polygon();
				   rightShoulder17.getPoints().addAll(new Double[]{ 
							1138.0,561.0,
							1152.0,561.0,
							1153.0,562.0,
							1153.0,563.0,
							1153.0,564.0,
							1139.0,597.0,
							1126.0,595.0,
								      });
				   Stop[] stops14 = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient14 = 
					         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops14);  
			      rightShoulder17.setFill(linearGradient14);
			      rightShoulder17.setStroke(Color.BLACK);
			      rightShoulder17.setStrokeWidth(2.0);
		      
			      Polygon rightShoulder18 = new Polygon();
				   rightShoulder18.getPoints().addAll(new Double[]{ 
							1138.0,561.0,
							1126.0,595.0,
							1134.0,595.0,
							1147.0,561.0,
									      });
				      rightShoulder18.setFill(Color.BLACK);
				      
				      Polygon rightShoulder19 = new Polygon();
					   rightShoulder19.getPoints().addAll(new Double[]{ 
								1102.0,646.0,
								1103.0,646.0,
								1112.0,658.0,
								1112.0,659.0,
								1080.0,676.0,
								1079.0,676.0,
								1070.0,664.0,
								1070.0,663.0,
									      });
					   Stop[] stops15 = new Stop[] { 
						         new Stop(1, Color.rgb(82, 125, 234)),  
						         new Stop(0, Color.rgb(42, 76, 162))
						      };  
						      LinearGradient linearGradient15 = 
						         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops15);  
				      rightShoulder19.setFill(linearGradient15);
				      rightShoulder19.setStroke(Color.BLACK);
				      rightShoulder19.setStrokeWidth(2.0);
				      
				      Polygon rightShoulder20 = new Polygon();
					   rightShoulder20.getPoints().addAll(new Double[]{ 
								1102.0,646.0,
								1103.0,646.0,
								1108.0,653.0,
								1082.0,668.0,
								1076.0,661.0,
										      });
				      rightShoulder20.setFill(Color.BLACK);
				      
				      Polygon rightShoulder21 = new Polygon();
					   rightShoulder21.getPoints().addAll(new Double[]{ 
								1118.0,532.0,
								1169.0,524.0,
								1176.0,526.0,
								1178.0,553.0,
								1166.0,574.0,
								1153.0,579.0,//
								1159.0,559.0,
								1144.0,533.0,
									      });
					   Stop[] stops16 = new Stop[] { 
						         new Stop(0, Color.rgb(255, 71, 26)),  
						         new Stop(1, Color.DARKRED),
						         
						      };  
						      LinearGradient linearGradient16 = 
						         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops16);  
				      rightShoulder21.setFill(linearGradient16);
				      rightShoulder21.setStroke(Color.BLACK);
				      rightShoulder21.setStrokeWidth(2.0);
				      
				      Polygon rightShoulder22 = new Polygon();
					   rightShoulder22.getPoints().addAll(new Double[]{ 
								1176.0,526.0,
								1191.0,524.0,
								1203.0,524.0,
								1205.0,525.0,
								1205.0,527.0,
								1205.0,529.0,
								1208.0,555.0,
								1207.0,556.0,
								1192.0,574.0,
								1180.0,574.0,
								1179.0,573.0,
								1178.0,553.0,
									      });
					   Stop[] stops17 = new Stop[] { 
						         new Stop(0, Color.rgb(255, 71, 26)),  
						         new Stop(1, Color.DARKRED),
						         
						      };  
						      LinearGradient linearGradient17 = 
						         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops17);  
				      rightShoulder22.setFill(linearGradient17);
				      rightShoulder22.setStroke(Color.BLACK);
				      rightShoulder22.setStrokeWidth(2.0);
				      
				      Polygon rightShoulder23 = new Polygon();
					   rightShoulder23.getPoints().addAll(new Double[]{ 
								1176.0,526.0,
								1191.0,524.0,
								1193.0,554.0,
								1180.0,574.0,
								1179.0,573.0,
								1178.0,553.0,
									      });
					   Stop[] stops18 = new Stop[] { 
						         new Stop(0, Color.rgb(255, 71, 26)),  
						         new Stop(1, Color.DARKRED),
						         
						      };  
						      LinearGradient linearGradient18 = 
						         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops18);   
				      rightShoulder23.setFill(linearGradient18);
				      rightShoulder23.setStroke(Color.BLACK);
				      rightShoulder23.setStrokeWidth(2.0);
				      
				      Polygon rightShoulder24 = new Polygon(); 
					   rightShoulder24.getPoints().addAll(new Double[]{ 
								1191.0,524.0,
								1203.0,524.0,
								1205.0,525.0,
								1205.0,529.0,
								1208.0,555.0,
								1207.0,556.0,
								1193.0,554.0,
									      });
					   Stop[] stops19 = new Stop[] { 
						         new Stop(0, Color.rgb(255, 71, 26)),  
						         new Stop(1, Color.DARKRED),
						         
						      };  
						      LinearGradient linearGradient19 = 
						         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops19); 
				      rightShoulder24.setFill(linearGradient19);
				      rightShoulder24.setStroke(Color.BLACK);
				      rightShoulder24.setStrokeWidth(2.0);
				      
				      Polygon rightShoulder25 = new Polygon();
					   rightShoulder25.getPoints().addAll(new Double[]{ 
								1192.0,529.0,
								1198.0,529.0,
								1199.0,530.0,
								1200.0,531.0,
								1201.0,547.0,
								1200.0,548.0,
								1199.0,549.0,
								1193.0,549.0,
										      });
				      rightShoulder25.setFill(Color.BLACK);
				      
				      Polygon rightShoulder26 = new Polygon();
					   rightShoulder26.getPoints().addAll(new Double[]{ 
								1193.0,554.0,
								1207.0,556.0,
								1192.0,574.0,
								1180.0,574.0,
										      });
					   Stop[] stops20 = new Stop[] { 
						         new Stop(0, Color.rgb(255, 71, 26)),  
						         new Stop(1, Color.DARKRED),
						         
						      };  
						      LinearGradient linearGradient20 = 
						         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops20); 	
					      rightShoulder26.setFill(linearGradient20);
					      rightShoulder26.setStroke(Color.BLACK);
					      rightShoulder26.setStrokeWidth(2.0);
				      
					      Polygon rightShoulder27 = new Polygon();
						   rightShoulder27.getPoints().addAll(new Double[]{ 
									1193.0,554.0,
									1200.0,556.0,
									1191.0,570.0,
									1184.0,570.0,
											      });
					      rightShoulder27.setFill(Color.BLACK); 
					      
					      Polygon rightShoulder28 = new Polygon();
						   rightShoulder28.getPoints().addAll(new Double[]{ 
									1180.0,574.0,
									1186.0,576.0,
									1186.0,577.0,
									1149.0,588.0,
									1152.0,579.0,
									1166.0,574.0,
									1178.0,553.0,
											      });
						   Stop[] stops21 = new Stop[] { 
							         new Stop(0, Color.rgb(255, 71, 26)),  
							         new Stop(1, Color.DARKRED),
							         
							      };  
							      LinearGradient linearGradient21 = 
							         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops21); 	
					      rightShoulder28.setFill(linearGradient21);
					      rightShoulder28.setStroke(Color.BLACK);
					      rightShoulder28.setStrokeWidth(2.0);
					      
					      Polygon rightShoulder29 = new Polygon();
						    rightShoulder29.getPoints().addAll(new Double[]{ 
									1205.0,529.0,
									1206.0,542.0,
									1211.0,558.0,
									1237.0,536.0,
									1238.0,536.0,
									1239.0,536.0,
									1242.0,538.0,
									1247.0,533.0,
									1247.0,518.0,
						    }); 
						    Light.Distant light = new Light.Distant(); 
						      
						      //Setting the properties of the light source 
						      light.setAzimuth(45.0); 
						      light.setElevation(30.0);       
						       
						      //Instantiating the Lighting class  
						      Lighting lighting = new Lighting(); 
						      
						      //Setting the source of the light 
						      lighting.setLight(light);
						      
						      rightShoulder29.setEffect(lighting);
						      rightShoulder29.setFill(Color.YELLOW);
						      rightShoulder29.setStroke(Color.BLACK);
						      rightShoulder29.setStrokeWidth(2.0);
						      
						      Polygon rightShoulder36 = new Polygon();
							   rightShoulder36.getPoints().addAll(new Double[]{ 
										1170.0,581.0,
										1174.0,586.0,
										1176.0,593.0,
										1183.0,581.0,
										1192.0,576.0,
														      });
						      rightShoulder36.setFill(Color.BLACK);
				      //////////////////////////////////////////////////
						      Polygon rightShoulder30 = new Polygon();
							   rightShoulder30.getPoints().addAll(new Double[]{ 
										1149.0,588.0,
										1134.0,630.0,
										1141.0,629.0,
										1144.0,631.0,
										1158.0,632.0,
										1155.0,629.0,
										1176.0,594.0,
										1174.0,587.0,
										1170.0,581.0,
														      });
								      rightShoulder30.setFill(Color.LIGHTGRAY);
								      rightShoulder30.setStroke(Color.BLACK);
								      rightShoulder30.setStrokeWidth(2.0);
							///////////////////////////////////////////////////////
		
																			      
																			      Polygon rightShoulder41 = new Polygon();
																				   rightShoulder41.getPoints().addAll(new Double[]{ 
																				    		 1143.0,366.0,
																				    		 1144.0,368.0,
																				    		 1146.0,372.0,
																				    		 1147.0,373.0,
																				    		 1148.0,376.0,
																				    		// 1145.0,379.0,
																				    		 1150.0,382.0,
																				    		 1151.0,388.0,
																				    		 1152.0,392.0,
																				    		 1153.0,397.0,
																				    		 1154.0,406.0,
																				    		 1154.0,451.0,
																				    		 1153.0,458.0,
																				    		 1152.0,460.0,
																				    		 1151.0,462.0,
																				    		 1150.0,464.0,
																				    		 1149.0,466.0,
																				    		 1159.0,466.0,
																				    		 1167.0,486.0,
																				    		 1195.0,481.0,
																				    		 1195.0,261.0,
																				    		 1186.0,254.0,
																				    		 1184.0,241.0,
																				    		 1143.0,292.0,
																									      });
																				   Stop[] stops26 = new Stop[] { 
																					         new Stop(1, Color.rgb(82, 125, 234)),  
																					         new Stop(0, Color.rgb(42, 76, 162))
																					      };  
																					      LinearGradient linearGradient26 = 
																					         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops26); 		
																				      rightShoulder41.setFill(linearGradient26);
																				      rightShoulder41.setStroke(Color.BLACK);
																				      rightShoulder41.setStrokeWidth(2.0);
																				      
																				      Polygon rightShoulder42 = new Polygon();
																					   rightShoulder42.getPoints().addAll(new Double[]{ 
																						    	1184.0,241.0,
																						    	1186.0,254.0,
																						    	1173.0,254.0,
																											      });
																					   Stop[] stops27 = new Stop[] { 
																						         new Stop(1, Color.rgb(82, 125, 234)),  
																						         new Stop(0, Color.rgb(42, 76, 162))
																						      };  
																						      LinearGradient linearGradient27 = 
																						         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops27); 		
																						      rightShoulder42.setFill(linearGradient27);
																						      rightShoulder42.setStroke(Color.BLACK);
																						      rightShoulder42.setStrokeWidth(2.0);
																						      
																						      Polygon rightShoulder43 = new Polygon();
																							   rightShoulder43.getPoints().addAll(new Double[]{ 
																								    	1186.0,254.0,
																								    	1195.0,261.0,
																								    	1195.0,304.0,
																								    	1143.0,304.0,
																								    	1143.0,292.0,
																								    	1173.0,254.0,
																													      });
																							   Stop[] stops28 = new Stop[] { 
																								         new Stop(1, Color.rgb(82, 125, 234)),  
																								         new Stop(0, Color.rgb(42, 76, 162))
																								      };  
																								      LinearGradient linearGradient28 = 
																								         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops28); 
																						      rightShoulder43.setFill(linearGradient28);
																						      rightShoulder43.setStroke(Color.BLACK);
																						      rightShoulder43.setStrokeWidth(2.0); 
								      
																						     
																						      
																						      Polygon rightShoulder46 = new Polygon();
																							   rightShoulder46.getPoints().addAll(new Double[]{ 
																								    	1134.0,630.0,
																								    	1136.0,646.0,
																								    	1127.0,651.0,
																													      });
																							   Stop[] stops29 = new Stop[] { 
																								         new Stop(0, Color.DARKRED),  
																								         new Stop(1, Color.rgb(255, 71, 26)),
																								         
																								      };  
																								      LinearGradient linearGradient29 = 
																								         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops29);   
																						      rightShoulder46.setFill(linearGradient29);
																						      rightShoulder46.setStroke(Color.BLACK);
																						      rightShoulder46.setStrokeWidth(2.0);
																						      
																						      Polygon rightShoulder47 = new Polygon();
																							   rightShoulder47.getPoints().addAll(new Double[]{ 
																								    	1136.0,646.0,
																								    	1127.0,651.0,
																								    	1125.0,658.0,
																								    	1113.0,664.0,
																								    	1138.0,663.0,
																													      });
																							   Stop[] stops30 = new Stop[] { 
																								         new Stop(0, Color.DARKRED),  
																								         new Stop(1, Color.rgb(255, 71, 26)),
																								         
																								      };  
																								      LinearGradient linearGradient30 = 
																								         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops30);  
																						      rightShoulder47.setFill(linearGradient30);
																						      rightShoulder47.setStroke(Color.BLACK);
																						      rightShoulder47.setStrokeWidth(2.0);
																						      
																						      Polygon gundamRightHandOne = new Polygon();
																							   gundamRightHandOne.getPoints().addAll(new Double[]{ 
																								    	1118.0,664.0,
																								    	1138.0,663.0,
																								    	1140.0,687.0,
																								    	1149.0,714.0,
																								    	1124.0,726.0,
																													      });
																							   Stop[] stops31 = new Stop[] { 
																								         new Stop(1, Color.rgb(82, 125, 234)),  
																								         new Stop(0, Color.rgb(42, 76, 162))
																								      };  
																								      LinearGradient linearGradient31 = 
																								         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops31);   
																						      gundamRightHandOne.setFill(linearGradient31);
																						      gundamRightHandOne.setStroke(Color.BLACK);
																						      gundamRightHandOne.setStrokeWidth(2.0);
																						      
																						      Polygon gundamRightHandTwo = new Polygon();
																							   gundamRightHandTwo.getPoints().addAll(new Double[]{ 
																								    	1118.0,664.0,
																								    	1124.0,726.0,
																								    	1097.0,733.0,
																								    	1099.0,740.0,
																								    	1097.0,741.0,
																								    	1092.0,734.0,
																								    	1096.0,703.0,
																								    	1092.0,694.0,
																								    	1094.0,674.0,
																								    	1113.0,664.0,
																													      });
																							   Stop[] stops32 = new Stop[] { 
																								         new Stop(1, Color.rgb(82, 125, 234)),  
																								         new Stop(0, Color.rgb(42, 76, 162))
																								      };  
																								      LinearGradient linearGradient32 = 
																								         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops32); 
																						      gundamRightHandTwo.setFill(linearGradient32);
																						      gundamRightHandTwo.setStroke(Color.BLACK);
																						      gundamRightHandTwo.setStrokeWidth(2.0);
																						      
																						      Polygon gundamRightHandThree = new Polygon();
																							   gundamRightHandThree.getPoints().addAll(new Double[]{ 
																										1118.0,664.0,
																										1121.0,698.0,
																										1111.0,689.0,
																										1110.0,666.0,
																											
																															      });
																							      gundamRightHandThree.setFill(Color.BLACK);
																							      Polygon gundamRightHandFour = new Polygon();
																								   gundamRightHandFour.getPoints().addAll(new Double[]{ 
																											1149.0,714.0,
																											1124.0,726.0,
																											1097.0,733.0,
																											1099.0,740.0,
																											1111.0,734.0,
																											1120.0,737.0,
																											1121.0,753.0,
																											1136.0,727.0,
																											1144.0,726.0,
																											1153.0,724.0,
																												
																																      });
																							      gundamRightHandFour.setFill(Color.BLACK);
																							      
																							      Polygon gundamRightHandFive = new Polygon();
																								   gundamRightHandFive.getPoints().addAll(new Double[]{ 
																								    		  
																									    	1121.0,753.0,
																									    	1120.0,737.0,
																									    	1111.0,735.0,
																									    	1099.0,740.0,
																									    	1097.0,741.0,
																									    	1086.0,747.0,
																									    	1082.0,776.0,
																									    	1083.0,779.0,
																									    	1084.0,782.0,
																									    	1084.0,784.0,
																									    	1088.0,785.0,
																									    	1087.0,778.0,
																									    	1097.0,768.0,
																									    	1108.0,767.0,
																														      });
																								   Stop[] stops33 = new Stop[] { 
																									         new Stop(1, Color.rgb(82, 125, 234)),  
																									         new Stop(0, Color.rgb(42, 76, 162))
																									      };  
																									      LinearGradient linearGradient33 = 
																									         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops33); 
																							      gundamRightHandFive.setFill(linearGradient33);
																							      gundamRightHandFive.setStroke(Color.BLACK);
																							      gundamRightHandFive.setStrokeWidth(2.0);
																							      
																							      Polygon gundamRightHandSix = new Polygon();
																								   gundamRightHandSix.getPoints().addAll(new Double[]{ 
																									    	1082.0,769.0,
																									    	1081.0,773.0,
																									    	1082.0,776.0,
																									    	1083.0,779.0,
																									    	1084.0,782.0,
																									    	1084.0,784.0,
																									    	1088.0,785.0,
																									    	1087.0,778.0,
																									    	1090.0,776.0,
																														      });
																								   Stop[] stops34 = new Stop[] { 
																									         new Stop(1, Color.rgb(82, 125, 234)),  
																									         new Stop(0, Color.rgb(42, 76, 162))
																									      };  
																									      LinearGradient linearGradient34 = 
																									         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops34);  
																							      gundamRightHandSix.setFill(linearGradient34);
																							      gundamRightHandSix.setStroke(Color.BLACK);
																							      gundamRightHandSix.setStrokeWidth(2.0);
																							      
																							      Polygon gundamRightHandSeven = new Polygon();
																								   gundamRightHandSeven.getPoints().addAll(new Double[]{ 
																									    	1153.0,724.0,				    	
																									    	1144.0,726.0,
																									    	1136.0,727.0,
																									    	1121.0,753.0,
																									    	1108.0,768.0,
																									    	1120.0,811.0,
																									    	1166.0,836.0,
																									    	1184.0,840.0,
																									    	1188.0,833.0,
																														      });
																								   Stop[] stops35 = new Stop[] { 
																									         new Stop(1, Color.rgb(82, 125, 234)),  
																									         new Stop(0, Color.rgb(42, 76, 162))
																									      };  
																									      LinearGradient linearGradient35 = 
																									         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops35); 
																							      gundamRightHandSeven.setFill(linearGradient35);
																							      gundamRightHandSeven.setStroke(Color.BLACK);
																							      gundamRightHandSeven.setStrokeWidth(2.0);
																							      
																							      Polygon gundamRightHandEight = new Polygon();
																								   gundamRightHandEight.getPoints().addAll(new Double[]{ 
																									    	1153.0,724.0,
																									    	1144.0,726.0,
																									    	1136.0,727.0,
																									    	1121.0,753.0,
																									    	1108.0,768.0,
																									    	1120.0,811.0,
																									    	1149.0,776.0,
																									    	1157.0,737.0,
																														      });
																								   Stop[] stops36 = new Stop[] { 
																									         new Stop(1, Color.rgb(82, 125, 234)),  
																									         new Stop(0, Color.rgb(42, 76, 162))
																									      };  
																									      LinearGradient linearGradient36 = 
																									         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops36); 
																							      gundamRightHandEight.setFill(linearGradient36);
																							      gundamRightHandEight.setStroke(Color.BLACK);
																							      gundamRightHandEight.setStrokeWidth(2.0);
																							      
																							      Polygon gundamRightHandNine = new Polygon();
																								   gundamRightHandNine.getPoints().addAll(new Double[]{ 
																									    	1108.0,768.0,
																									    	1097.0,768.0,
																									    	1087.0,778.0,
																									    	1088.0,798.0,
																									    	1104.0,815.0,
																									    	1123.0,813.0,
																									    	1120.0,811.0,
																														      });
																								   Stop[] stops37 = new Stop[] { 
																									         new Stop(1, Color.rgb(82, 125, 234)),  
																									         new Stop(0, Color.rgb(42, 76, 162))
																									      };  
																									      LinearGradient linearGradient37 = 
																									         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops37);  
																							      gundamRightHandNine.setFill(linearGradient37);
																							      gundamRightHandNine.setStroke(Color.BLACK);
																							      gundamRightHandNine.setStrokeWidth(2.0);
																							      
																							      Polygon gundamRightHandTen = new Polygon();
																								   gundamRightHandTen.getPoints().addAll(new Double[]{ 
																									    	1108.0,768.0,
																									    	1097.0,768.0,
																									    	1087.0,778.0,
																									    	1088.0,798.0,
																									    	1090.0,800.0,
																									    	1102.0,782.0,
																									    	1112.0,782.0,
																														      });
																								   Stop[] stops38 = new Stop[] { 
																									         new Stop(1, Color.rgb(82, 125, 234)),  
																									         new Stop(0, Color.rgb(42, 76, 162))
																									      };  
																									      LinearGradient linearGradient38 = 
																									         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops38);   
																							      gundamRightHandTen.setFill(linearGradient38);
																							      gundamRightHandTen.setStroke(Color.BLACK);
																							      gundamRightHandTen.setStrokeWidth(2.0);
																							      
																							      Polygon gundamRightHand11 = new Polygon();
																								   gundamRightHand11.getPoints().addAll(new Double[]{ 
																										    1123.0,813.0,
																										    1111.0,815.0,
																										    1111.0,819.0,
																										    1123.0,827.0,
																										    1127.0,828.0,
																										    1130.0,827.0,
																										    1137.0,821.0,
																															      });
																								   
																								   Stop[] stops39 = new Stop[] { 
																									         new Stop(1, Color.rgb(82, 125, 234)),  
																									         new Stop(0, Color.rgb(42, 76, 162))
																									      };  
																									      LinearGradient linearGradient39 = 
																									         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops39); 	
																								      gundamRightHand11.setFill(linearGradient39);
																								      gundamRightHand11.setStroke(Color.BLACK);
																								      gundamRightHand11.setStrokeWidth(2.0);
																								      
																								      Polygon gundamRightHand12 = new Polygon();
																									   gundamRightHand12.getPoints().addAll(new Double[]{ 
																											    1137.0,821.0,
																											    1130.0,827.0,
																											    1133.0,830.0,
																											    1138.0,832.0,
																											    1143.0,832.0,
																											    1146.0,832.0,
																											    1151.0,829.0,
																																      });
																									   Stop[] stops40 = new Stop[] { 
																										         new Stop(1, Color.rgb(82, 125, 234)),  
																										         new Stop(0, Color.rgb(42, 76, 162))
																										      };  
																										      LinearGradient linearGradient40 = 
																										         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops40); 	
																									      gundamRightHand12.setFill(linearGradient40);
																									      gundamRightHand12.setStroke(Color.BLACK);
																									      gundamRightHand12.setStrokeWidth(2.0);
																									      
																									      Polygon gundamRightHand13 = new Polygon();
																										   
																									      gundamRightHand13.getPoints().addAll(new Double[]{ 
																									    		  1151.0,829.0,
																									    		  1146.0,834.0,
																									    		  1147.0,835.0,
																									    		  1150.0,837.0,
																									    		  1152.0,838.0,
																									    		  1161.0,839.0,
																									    		  1167.0,837.0,
																																	      });
																									      Stop[] stops41 = new Stop[] { 
																											         new Stop(1, Color.rgb(82, 125, 234)),  
																											         new Stop(0, Color.rgb(42, 76, 162))
																											      };  
																											      LinearGradient linearGradient41 = 
																											         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops41); 	
																										      gundamRightHand13.setFill(linearGradient41);
																										      gundamRightHand13.setStroke(Color.BLACK);
																										      gundamRightHand13.setStrokeWidth(2.0);
																										      
																										      Polygon leftShoulder2 = new Polygon();
																											   leftShoulder2.getPoints().addAll(new Double[]{ 
																											    		  793.0,474.0,
																											    		  768.0,469.0,
																											    		  752.0,468.0,
																											    		  744.0,490.0,
																											    		  744.0,492.0,
																											    		  765.0,495.0,
																											    		  791.0,501.0,
																																			      });
																											   Stop[] stops42 = new Stop[] { 
																												         new Stop(0, Color.DARKRED),  
																												         new Stop(1, Color.rgb(255, 71, 26)),
																												         
																												      };  
																												      LinearGradient linearGradient42 = 
																												         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops42); 	
																											      leftShoulder2.setFill(linearGradient42);
																											      leftShoulder2.setStroke(Color.BLACK);
																											      leftShoulder2.setStrokeWidth(2.0);
																											      
																											      Polygon leftShoulder1 = new Polygon();
																												   
																											      leftShoulder1.getPoints().addAll(new Double[]{ 
																											    		  793.0,474.0,
																											    		  771.0,472.0,
																											    		  768.0,472.0,
																											    		  767.0,475.0,
																											    		  765.0,495.0,
																											    		  791.0,501.0,
																																			      });
																											      Stop[] stops43 = new Stop[] { 
																													         new Stop(0, Color.DARKRED),  
																													         new Stop(1, Color.rgb(255, 71, 26)),
																													         
																													      };  
																													      LinearGradient linearGradient43 = 
																													         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops43); 
																											      leftShoulder1.setFill(linearGradient43);
																											      leftShoulder1.setStroke(Color.BLACK);
																											      leftShoulder1.setStrokeWidth(2.0);
																											      
																											      Polygon leftShoulder3 = new Polygon();
																												   leftShoulder3.getPoints().addAll(new Double[]{ 
																												    		  791.0,501.0,
																												    		  765.0,495.0,
																												    		  744.0,492.0,
																												    		  744.0,490.0,
																												    		  745.0,486.0,
																												    		  587.0,456.0,
																												    		  553.0,457.0,
																												    		  786.0,506.0,
																												    		  788.0,508.0,
																												    		  789.0,509.0,
																												    		  790.0,511.0,
																												    		  790.0,513.0,
																												    		  790.0,514.0,
																												    		  791.0,514.0,
																																				      });
																												   Stop[] stops44 = new Stop[] { 
																													         new Stop(0, Color.DARKRED),  
																													         new Stop(1, Color.rgb(255, 71, 26)),
																													         
																													      };  
																													      LinearGradient linearGradient44 = 
																													         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops44); 
																												      leftShoulder3.setFill(linearGradient44);
																												      leftShoulder3.setStroke(Color.BLACK);
																												      leftShoulder3.setStrokeWidth(2.0);
																												      
																												      Polygon leftShoulder4 = new Polygon();
																													   leftShoulder4.getPoints().addAll(new Double[]{ 
																													    		  791.0,514.0,
																													    		  790.0,514.0,
																													    		  790.0,513.0,
																													    		  790.0,511.0,
																													    		  789.0,509.0,
																													    		  788.0,508.0,
																													    		  786.0,506.0,
																													    		  553.0,458.0,
																													    		  608.0,503.0,
																													    		  629.0,493.0,
																													    		  630.0,493.0,
																													    		  780.0,536.0,
																													    		  785.0,536.0,
																													    		  787.0,535.0,
																													    		  788.0,534.0,
																													    		  790.0,534.0,
																													    		  791.0,533.0,
																													    		  791.0,532.0,
																																					      });
																													   Stop[] stops45 = new Stop[] { 
																														         new Stop(0, Color.DARKRED),  
																														         new Stop(1, Color.rgb(255, 71, 26)),
																														         
																														      };  
																														      LinearGradient linearGradient45 = 
																														         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops45); 	
																													      leftShoulder4.setFill(linearGradient45);
																													      leftShoulder4.setStroke(Color.BLACK);
																													      leftShoulder4.setStrokeWidth(2.0);
																													      
																													      Polygon leftShoulder5 = new Polygon();
																														   leftShoulder5.getPoints().addAll(new Double[]{ 
																														    		 768.0,512.0,
																														    		 770.0,510.0,
																														    		 773.0,509.0,
																														    		 776.0,508.0,
																														    		 780.0,509.0,
																														    		 783.0,511.0,
																														    		 785.0,512.0,
																														    		 788.0,517.0,
																														    		 788.0,526.0,
																														    		 785.0,530.0,
																														    		 779.0,533.0,
																														    		 772.0,532.0,
																														    		 767.0,529.0,
																														    		 764.0,524.0,
																														    		 769.0,520.0,
																																						      });
																														   Stop[] stops46 = new Stop[] { 
																															         new Stop(0, Color.DARKRED),  
																															         new Stop(1, Color.rgb(255, 71, 26)),
																															         
																															      };  
																															      LinearGradient linearGradient46 = 
																															         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops46); 	
																														      leftShoulder5.setFill(linearGradient46);
																														      leftShoulder5.setStroke(Color.BLACK);
																														      leftShoulder5.setStrokeWidth(2.0);
																														      Polygon leftShoulder6 = new Polygon();
																															   leftShoulder6.getPoints().addAll(new Double[]{ 
																															    		769.0,518.0,
																															    		771.0,516.0,
																															    		774.0,514.0,
																															    		775.0,514.0,
																															    		777.0,514.0,
																															    		781.0,517.0,
																															    		782.0,519.0,
																															    		782.0,520.0,
																															    		782.0,521.0,
																															    		780.0,525.0,
																															    		779.0,526.0,
																															    		777.0,527.0,
																															    		774.0,527.0,
																															    		770.0,524.0,
																															    		769.0,521.0,
																																							      });
																															      leftShoulder6.setFill(Color.BLACK);	
																															      
				 Polygon leftShoulder7 = new Polygon();
				 leftShoulder7.getPoints().addAll(new Double[]{ 
				 768.0,512.0,
				 769.0,520.0,
				 764.0,524.0,
				 711.0,504.0,
				 });
				Stop[] stops47 = new Stop[] { 
					new Stop(0, Color.DARKRED),  
					new Stop(1, Color.rgb(255, 71, 26)),
																																	         
				};  
				LinearGradient linearGradient47 = new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops47);  
				leftShoulder7.setFill(linearGradient47);
				 leftShoulder7.setStroke(Color.BLACK);
				leftShoulder7.setStrokeWidth(2.0);	
				
				 Polygon leftShoulder8 = new Polygon();
				   leftShoulder8.getPoints().addAll(new Double[]{ 
				    		 781.0,537.0,
				    		 726.0,521.0,
				    		 723.0,540.0,
				    		 726.0,543.0,
				    		 731.0,534.0,
				    		 761.0,534.0,
				    		 778.0,538.0,
												      });
				   Stop[] stops48 = new Stop[] { 
					         new Stop(0, Color.DARKRED),  
					         new Stop(1, Color.rgb(255, 71, 26)),
					         
					      };  
					      LinearGradient linearGradient48 = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops48);   
			      leftShoulder8.setFill(linearGradient48);
			      leftShoulder8.setStroke(Color.BLACK);
			      leftShoulder8.setStrokeWidth(2.0);
			      
			      Polygon leftShoulder9 = new Polygon();
				   leftShoulder9.getPoints().addAll(new Double[]{ 
				    		 726.0,521.0,
				    		 723.0,540.0,
				    		 726.0,543.0,
				    		 717.0,559.0,
				    		 710.0,545.0,
				    		 714.0,518.0,
												      });
				   Stop[] stops49 = new Stop[] { 
					        // new Stop(0, Color.DARKRED), 
					         new Stop(0, Color.DARKRED),
					         new Stop(1, Color.rgb(255, 71, 26)),
					         
					      };  
					      LinearGradient linearGradient49 = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops49); 
			      leftShoulder9.setFill(linearGradient49);
			      leftShoulder9.setStroke(Color.BLACK);
			      leftShoulder9.setStrokeWidth(2.0);
			      
			      Polygon leftShoulder10 = new Polygon();
				   leftShoulder10.getPoints().addAll(new Double[]{ 
				    		 761.0,534.0,
				    		 731.0,534.0,
				    		 717.0,559.0,
				    		 731.0,637.0,
				    		 766.0,668.0,
				    		 766.0,630.0,
				    		 783.0,593.0,
				    		 784.0,580.0,
				    		 798.0,564.0,
				    		 798.0,557.0,
				    		 788.0,541.0,
				    		 787.0,541.0,
												      });
				   Stop[] stops50 = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient50 = 
					         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops50);   
			      leftShoulder10.setFill(linearGradient50);
			      leftShoulder10.setStroke(Color.BLACK);
			      leftShoulder10.setStrokeWidth(2.0);
			      
			      Polygon leftShoulder11 = new Polygon();
				   leftShoulder11.getPoints().addAll(new Double[]{ 
				    		 731.0,534.0,
				    		 717.0,559.0,
				    		 731.0,637.0,
				    		 766.0,668.0,
				    		 766.0,630.0,
				    		 783.0,593.0,
				    		 784.0,580.0,
				    		 788.0,563.0,
				    		 777.0,543.0,
												      });
				   Stop[] stops51 = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient51 = 
					         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops51);  
			      leftShoulder11.setFill(linearGradient51);
			      leftShoulder11.setStroke(Color.BLACK);
			      leftShoulder11.setStrokeWidth(2.0);
			      
			      Polygon leftShoulder12 = new Polygon();
				   
			      leftShoulder12.getPoints().addAll(new Double[]{ 
				    	731.0,637.0,
				    	766.0,668.0,
				    	766.0,671.0,
				    	770.0,676.0,
				    	770.0,680.0,
				    	738.0,655.0,
												      });
			      Stop[] stops52 = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient52 = 
					         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops52);  
			      leftShoulder12.setFill(linearGradient52);
			      leftShoulder12.setStroke(Color.BLACK);
			      leftShoulder12.setStrokeWidth(2.0);
				  
			      Polygon leftShoulder13 = new Polygon();
				   leftShoulder13.getPoints().addAll(new Double[]{ 
					    	733.0,578.0,
					    	735.0,575.0,
					    	738.0,573.0,
					    	771.0,578.0,
					    	773.0,579.0,
					    	775.0,583.0,
					    	775.0,600.0,
					    	773.0,602.0,
					    	770.0,604.0,
					    	736.0,599.0,
					    	733.0,597.0,
					    	732.0,594.0,
													      });
				   Stop[] stops53 = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient53 = 
					         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops53); 
			      leftShoulder13.setFill(linearGradient53);
			      leftShoulder13.setStroke(Color.BLACK);
			      leftShoulder13.setStrokeWidth(2.0);
			      
			      Polygon leftShoulder14 = new Polygon();
				   leftShoulder14.getPoints().addAll(new Double[]{ 
					    	758.0,664.0,
					    	758.0,666.0,
					    	756.0,666.0,
					    	742.0,652.0,
					    	742.0,650.0,
					    	744.0,650.0,
													      });
			      leftShoulder14.setFill(Color.BLACK);
			      
			      Polygon leftShoulder15 = new Polygon();
				   leftShoulder15.getPoints().addAll(new Double[]{ 
					    	609.0,502.0,
					    	629.0,493.0,
					    	658.0,501.0,
													      });
				   Stop[] stops54 = new Stop[] { 
					        // new Stop(0, Color.DARKRED), 
						   new Stop(0, Color.DARKRED),
					         new Stop(1, Color.rgb(255, 71, 26)),
					         
					      };  
					      LinearGradient linearGradient54 = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops54); 
			      leftShoulder15.setFill(linearGradient54);
			      leftShoulder15.setStroke(Color.BLACK);
			      leftShoulder15.setStrokeWidth(2.0);
			      

			      
			      Polygon leftShoulder20 = new Polygon();
				   leftShoulder20.getPoints().addAll(new Double[]{ 
					    	731.0,637.0,
					    	716.0,638.0,
					    	673.0,711.0,
					    	678.0,728.0,
					    	722.0,670.0,
					    	756.0,670.0,
					    	738.0,655.0,
													      });
				   Stop[] stops59 = new Stop[] { 
					       
						   	new Stop(0, Color.DARKRED), 
					         new Stop(1, Color.rgb(255, 71, 26)),
					         
					      };  
					      LinearGradient linearGradient59 = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops59); 
			      leftShoulder20.setFill(linearGradient59);
			      leftShoulder20.setStroke(Color.BLACK);
			      leftShoulder20.setStrokeWidth(2.0);
			      
			      Polygon gundamLeftHandOne = new Polygon();
				   gundamLeftHandOne.getPoints().addAll(new Double[]{ 
					    	722.0,670.0,
					    	695.0,706.0,
					    	695.0,708.0,
					    	695.0,709.0,
					    	717.0,726.0,
					    	718.0,726.0,
					    	719.0,726.0,
					    	743.0,673.0,
					    	743.0,672.0,
					    	743.0,671.0,
					    	743.0,670.0,
													      });
				   Stop[] stops60= new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient60 = 
					         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops60);
				   
			      gundamLeftHandOne.setFill(linearGradient60);
			      gundamLeftHandOne.setStroke(Color.BLACK);
			      gundamLeftHandOne.setStrokeWidth(2.0);
			      
			      Polygon gundamLeftHandTwo = new Polygon();
				   gundamLeftHandTwo.getPoints().addAll(new Double[]{ 
					    	745.0,670.0,
					    	721.0,725.0,
					    	721.0,727.0,
					    	721.0,728.0,
					    	749.0,740.0,
					    	750.0,740.0,
					    	751.0,740.0,
					    	760.0,754.0,
					    	761.0,754.0,
					    	762.0,754.0,
					    	777.0,720.0,
					    	787.0,713.0,
					    	792.0,713.0,
					    	784.0,694.0,
					    	784.0,689.0,
					    	783.0,688.0,
					    	779.0,694.0,
					    	778.0,694.0,
					    	777.0,694.0,
					    	776.0,693.0,
					    	772.0,683.0,
					    	757.0,670.0,
													      });
				   Stop[] stops61 = new Stop[] { 
					         new Stop(1, Color.rgb(82, 125, 234)),  
					         new Stop(0, Color.rgb(42, 76, 162))
					      };  
					      LinearGradient linearGradient61 = 
					         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops61);
			      gundamLeftHandTwo.setFill(linearGradient61);
			      gundamLeftHandTwo.setStroke(Color.BLACK);
			      gundamLeftHandTwo.setStrokeWidth(2.0);
			      
			      Polygon gundamLeftHandThree = new Polygon();
				   gundamLeftHandThree.getPoints().addAll(new Double[]{ 
					    	743.0,670.0,
					    	731.0,702.0,
					    	745.0,691.0,
					    	755.0,670.0,
													      });
			      gundamLeftHandThree.setFill(Color.BLACK);
			      
			      Polygon gundamLeftHandFour = new Polygon();
				   gundamLeftHandFour.getPoints().addAll(new Double[]{ 
				    		  762.0,754.0,
				    		  751.0,740.0,
				    		  750.0,740.0,
				    		  749.0,740.0,
				    		  721.0,728.0,
				    		  721.0,727.0,
				    		  721.0,725.0,
				    		  719.0,726.0,
				    		  718.0,726.0,
				    		  717.0,726.0,
				    		  695.0,709.0,
				    		  695.0,708.0,
				    		  695.0,706.0,
				    		  678.0,728.0,
				    		  684.0,733.0,
				    		  690.0,719.0,
				    		  691.0,718.0,
				    		  692.0,718.0,
				    		  711.0,727.0,
				    		  710.0,749.0,
				    		  714.0,767.0,
				    		  714.0,768.0,
				    		  709.0,773.0,
				    		  710.0,773.0,
				    		  711.0,774.0,
				    		  720.0,782.0,
				    		  721.0,783.0,
				    		  721.0,786.0,
				    		  722.0,786.0,
				    		  725.0,783.0,
				    		  728.0,783.0,
				    		  728.0,780.0,
				    		  726.0,775.0,
				    		  724.0,774.0,
				    		  724.0,769.0,
				    		  723.0,767.0,
				    		  721.0,765.0,
				    		  720.0,761.0,
				    		  719.0,757.0,
				    		  718.0,753.0,
				    		  716.0,751.0,
				    		  716.0,741.0,
				    		  716.0,740.0,
				    		  729.0,734.0,
				    		  734.0,735.0,
				    		  737.0,736.0,
				    		  741.0,738.0,
				    		  744.0,740.0,
				    		  748.0,746.0,
				    		  748.0,748.0,
				    		  752.0,751.0,
				    		  760.0,762.0,
				    		  
						    	
														      });
				      gundamLeftHandFour.setFill(Color.BLACK);
				      
				      Polygon gundamLeftHandFive = new Polygon();
					   gundamLeftHandFive.getPoints().addAll(new Double[]{ 
							    682.0,733.0,
							    690.0,719.0,
							    691.0,718.0,
							    692.0,718.0,
							    711.0,727.0,
							    710.0,749.0,
							    714.0,767.0,
							    714.0,768.0,
							    709.0,773.0,
							    682.0,798.0,
							    681.0,798.0,
							    672.0,790.0,
							    672.0,755.0,
															      });
					   Stop[] stops62 = new Stop[] { 
						         new Stop(1, Color.rgb(82, 125, 234)),  
						         new Stop(0, Color.rgb(42, 76, 162))
						      };  
						      LinearGradient linearGradient62 = 
						         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops62);	
					      gundamLeftHandFive.setFill(linearGradient62);
					      gundamLeftHandFive.setStroke(Color.BLACK);
					      gundamLeftHandFive.setStrokeWidth(2.0);
					      
					      Polygon gundamLeftHandSix = new Polygon();
						   gundamLeftHandSix.getPoints().addAll(new Double[]{ 
								    684.0,796.0,
								    690.0,802.0,
								    714.0,819.0,
								    715.0,819.0,
								    720.0,816.0,
								    721.0,786.0,
								    721.0,783.0,
								    720.0,782.0,
								    711.0,774.0,
								    710.0,773.0,
								    709.0,773.0,
																      });
						   Stop[] stops63 = new Stop[] { 
							         new Stop(1, Color.rgb(82, 125, 234)),  
							         new Stop(0, Color.rgb(42, 76, 162))
							      };  
							      LinearGradient linearGradient63 = 
							         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops63);	 
					      gundamLeftHandSix.setFill(linearGradient63);
					      gundamLeftHandSix.setStroke(Color.BLACK);
					      gundamLeftHandSix.setStrokeWidth(2.0);
					      
					      Polygon gundamLeftHandSeven = new Polygon();
						   gundamLeftHandSeven.getPoints().addAll(new Double[]{ 
								   722.0,786.0,
								   725.0,783.0,
								   728.0,783.0,
								   742.0,795.0,
								   748.0,811.0,
								   733.0,818.0,
								   721.0,818.0,
								   720.0,816.0,
																      });
						   Stop[] stops64 = new Stop[] { 
							         new Stop(1, Color.rgb(82, 125, 234)),  
							         new Stop(0, Color.rgb(42, 76, 162))
							      };  
							      LinearGradient linearGradient64 = 
							         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops64); 
					      gundamLeftHandSeven.setFill(linearGradient64);
					      gundamLeftHandSeven.setStroke(Color.BLACK);
					      gundamLeftHandSeven.setStrokeWidth(2.0);
					      
					      Polygon gundamLeftHandEight = new Polygon();
						   gundamLeftHandEight.getPoints().addAll(new Double[]{ 
									  728.0,783.0,
									  743.0,795.0,
									  741.0,786.0,
									  747.0,781.0,
									  741.0,775.0,
									  728.0,780.0,
																	      });
						   Stop[] stops65 = new Stop[] { 
							         new Stop(1, Color.rgb(82, 125, 234)),  
							         new Stop(0, Color.rgb(42, 76, 162))
							      };  
							      LinearGradient linearGradient65 = 
							         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops65); 		 
						      gundamLeftHandEight.setFill(linearGradient65);
						      gundamLeftHandEight.setStroke(Color.BLACK);
						      gundamLeftHandEight.setStrokeWidth(2.0);
						      
						      Polygon gundamLeftHandNine = new Polygon();
							   gundamLeftHandNine.getPoints().addAll(new Double[]{ 
										  728.0,780.0,
										  726.0,779.0,
										  726.0,776.0,
										  736.0,770.0,
										  741.0,775.0,
																		      });
							   Stop[] stops66 = new Stop[] { 
								         new Stop(1, Color.rgb(82, 125, 234)),  
								         new Stop(0, Color.rgb(42, 76, 162))
								      };  
								      LinearGradient linearGradient66 = 
								         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops66); 		 
							      
							      gundamLeftHandNine.setFill(linearGradient66);
							      gundamLeftHandNine.setStroke(Color.BLACK);
							      gundamLeftHandNine.setStrokeWidth(2.0);
							  
							      Polygon gundamLeftHandTen = new Polygon();
								   gundamLeftHandTen.getPoints().addAll(new Double[]{ 
											  748.0,748.0,
											  748.0,746.0,
											  744.0,740.0,
											  741.0,738.0,
											  737.0,736.0,
											  734.0,733.0,
											  729.0,734.0,
											  716.0,740.0,
											  716.0,741.0,
											  716.0,751.0,
											  718.0,753.0,
											  719.0,757.0,
											  720.0,761.0,
											  721.0,765.0,
											  723.0,767.0,
											  724.0,769.0,
											  744.0,745.0,
											  745.0,745.0,
																			      });
								   Stop[] stops67 = new Stop[] { 
									         new Stop(1, Color.rgb(82, 125, 234)),  
									         new Stop(0, Color.rgb(42, 76, 162))
									      };  
									      LinearGradient linearGradient67 = 
									         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops67); 		
								      gundamLeftHandTen.setFill(linearGradient67);
								      gundamLeftHandTen.setStroke(Color.BLACK);
								      gundamLeftHandTen.setStrokeWidth(2.0);
						      
								      Polygon gundamLeftHand11 = new Polygon();
									   gundamLeftHand11.getPoints().addAll(new Double[]{ 
												  724.0,769.0,
												  744.0,745.0,
												  745.0,745.0,
												  748.0,748.0,
												  748.0,746.0,
												  750.0,751.0,
												  726.0,775.0,
												  724.0,774.0,
																				      });
									   Stop[] stops68 = new Stop[] { 
										         new Stop(0, Color.GOLD),  
										         new Stop(1, Color.rgb(237, 220, 114))
										        
										         
										      };  
										      LinearGradient linearGradient68 = 
										         new LinearGradient(1, 0, 0, 0, true, CycleMethod.NO_CYCLE, stops68); 
									      gundamLeftHand11.setFill(linearGradient68);
									      gundamLeftHand11.setStroke(Color.BLACK);
									      gundamLeftHand11.setStrokeWidth(2.0);  
									      
									      Polygon gundamLeftHand12 = new Polygon();
										   gundamLeftHand12.getPoints().addAll(new Double[]{ 
										    		  751.0,740.0,
										    		  760.0,754.0,
										    		  761.0,754.0,
										    		  762.0,754.0,
										    		  777.0,720.0,
										    		  787.0,713.0,
										    		  792.0,713.0,
										    		  784.0,694.0,
										    		  784.0,689.0,
										    		  779.0,697.0,
										    		  776.0,700.0,
										    		  769.0,706.0,
																					      });
										   Stop[] stops69 = new Stop[] { 
											         new Stop(1, Color.rgb(82, 125, 234)),  
											         new Stop(0, Color.rgb(42, 76, 162))
											      };  
											      LinearGradient linearGradient69 = 
											         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops69);
										      gundamLeftHand12.setFill(linearGradient69);
										      gundamLeftHand12.setStroke(Color.BLACK);
										      gundamLeftHand12.setStrokeWidth(2.0);
											
										      Polygon leftShoulder21 = new Polygon();
											   leftShoulder21.getPoints().addAll(new Double[]{ 
											    		  777.0,538.0,
											    		  782.0,536.0,
											    		  785.0,536.0,
											    		  788.0,536.0,
											    		  790.0,534.0,
											    		  792.0,533.0,
											    		  794.0,542.0,
											    		  797.0,551.0,
											    		  800.0,556.0,
											    		  803.0,561.0,
											    		  809.0,570.0,
											    		  816.0,577.0,
											    		  819.0,583.0,
											    		  805.0,580.0,
											    		  799.0,565.0,
											    		  798.0,556.0,
											    		  788.0,540.0,
																						      });
											      leftShoulder21.setFill(Color.BLACK);
											  
											    
												      
												      
											      
		      Group b = new Group(rightShoulderTwo,rightShoulderOne,rightShoulderThree,rightShoulderFour,rightShoulderFive,
		    		  rightShoulderSix,rightShoulderSeven,rightShoulderEight,rightShoulderNine,rightShoulderTen,rightShoulder12,rightShoulder11,rightShoulder13,
		    		  rightShoulder14,rightShoulder15,rightShoulder16,rightShoulder17,rightShoulder18,rightShoulder19,rightShoulder20,rightShoulder21,rightShoulder22,
		    		  rightShoulder23,rightShoulder24,rightShoulder25,rightShoulder26,rightShoulder27,rightShoulder28,rightShoulder29,rightShoulder30,rightShoulder36,
		    		  rightShoulder41,rightShoulder42,rightShoulder43,rightShoulder46,rightShoulder47,gundamRightHandOne,gundamRightHandTwo,
		    		  gundamRightHandThree,gundamRightHandFour,gundamRightHandFive,gundamRightHandSix,gundamRightHandSeven,gundamRightHandEight,gundamRightHandNine,gundamRightHandTen,
		    		  gundamRightHand11,gundamRightHand12,gundamRightHand13,leftShoulder2,leftShoulder1,leftShoulder3,leftShoulder4,leftShoulder5,leftShoulder6,leftShoulder7,leftShoulder8,
		    		  leftShoulder9,leftShoulder10,leftShoulder11,leftShoulder12,leftShoulder13,leftShoulder14,leftShoulder15,leftShoulder20,gundamLeftHandOne,gundamLeftHandTwo,gundamLeftHandThree,gundamLeftHandFour,gundamLeftHandFive,gundamLeftHandSix,
		    		  gundamLeftHandSeven,gundamLeftHandEight,gundamLeftHandNine,gundamLeftHandTen,gundamLeftHand11,gundamLeftHand12,leftShoulder21);
		      
		   
		    
		      
		      
		      return b;
		   }
		   public Node rotateTwo() {
			      Polygon rightShoulder31 = new Polygon();
						   rightShoulder31.getPoints().addAll(new Double[]{ 
									1155.0,629.0,
									1184.0,582.0,
									1211.0,558.0,
									1237.0,536.0,
									1239.0,536.0,
									1270.0,556.0,
									1270.0,557.0,
									1270.0,558.0,
									1270.0,560.0,
									1269.0,564.0,
									1231.0,666.0,
									1228.0,669.0,
									1224.0,669.0,
									1221.0,667.0,
									1220.0,639.0,
									1201.0,626.0,
									1192.0,641.0,
									1182.0,645.0,
									1158.0,632.0,
													      });
						   //
						   Stop[] stops22 = new Stop[] { 
							         new Stop(0, Color.rgb(255, 71, 26)),  
							         new Stop(1, Color.DARKRED),
							         
							      };  
							      LinearGradient linearGradient22 = 
							         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops22); 	
							      rightShoulder31.setFill(linearGradient22);
							      rightShoulder31.setStroke(Color.BLACK);
							      rightShoulder31.setStrokeWidth(2.0);	
							      
							      Polygon rightShoulder32 = new Polygon();
								   
							      rightShoulder32.getPoints().addAll(new Double[]{ 
											1228.0,669.0,
											1224.0,669.0,
											1221.0,667.0,
											1220.0,639.0,
											1201.0,626.0,
											1192.0,641.0,
											1182.0,645.0,
											1158.0,632.0,
											1198.0,624.0,
											1238.0,586.0,
											1224.0,639.0,
															      });
							    //Instantiating the Light.Distant class
							      Light.Distant lightThree = new Light.Distant(); 
							      
							      //Setting the properties of the light source 
							      lightThree.setAzimuth(45.0); 
							      lightThree.setElevation(30.0);       
							       
							      //Instantiating the Lighting class  
							      Lighting lightingThree = new Lighting(); 
							      
							      //Setting the source of the light 
							      lightingThree.setLight(lightThree);
							      
							      rightShoulder32.setEffect(lightingThree);
							      //YELLOW
									      rightShoulder32.setFill(Color.YELLOW);
									      rightShoulder32.setStroke(Color.BLACK);
									      rightShoulder32.setStrokeWidth(2.0);
									      
									      Polygon rightShoulder33 = new Polygon();
										   rightShoulder33.getPoints().addAll(new Double[]{ 
													1240.0,546.0,
													1240.0,544.0,
													1240.0,543.0,
													1239.0,543.0,
													1236.0,543.0,
													1225.0,553.0,
													1225.0,555.0,
													1226.0,556.0,
													1229.0,556.0,
																	      });
											      rightShoulder33.setFill(Color.BLACK);	
											      
											      Polygon rightShoulder34 = new Polygon();
												   rightShoulder34.getPoints().addAll(new Double[]{ 
															1223.0,556.0,
															1224.0,556.0,
															1224.0,557.0,
															1224.0,560.0,
															1213.0,569.0,
															1211.0,569.0,
															1210.0,569.0,
															1209.0,568.0,
															1209.0,566.0,
															1222.0,555.0,
															
																			      });
													      rightShoulder34.setFill(Color.BLACK);	
													      
													      Polygon rightShoulder35 = new Polygon();
														   rightShoulder35.getPoints().addAll(new Double[]{ 
																	1207.0,569.0,
																	1208.0,571.0,
																	1208.0,573.0,
																	1196.0,583.0,
																	1193.0,583.0,
																	1192.0,582.0,
																	1192.0,579.0,
																	1204.0,569.0,
																	
																	
																					      });
															rightShoulder35.setFill(Color.BLACK);
															
														      
														      Polygon rightShoulder37 = new Polygon();
															   rightShoulder37.getPoints().addAll(new Double[]{ 
																		1201.0,626.0,
																		1192.0,641.0,
																		1182.0,645.0,
																		1190.0,650.0,
																		1195.0,682.0,
																		1196.0,685.0,
																		1197.0,686.0,
																		1206.0,689.0,
																		1207.0,689.0,
																		1214.0,683.0,
																		1215.0,682.0,
																		1212.0,635.0,
																						      });
															   Stop[] stops23 = new Stop[] { 
																         new Stop(0, Color.DARKRED),  
																         new Stop(1, Color.rgb(255, 71, 26)),
																         
																      };  
																      LinearGradient linearGradient23 = 
																         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops23);  
														      rightShoulder37.setFill(linearGradient23);
														      rightShoulder37.setStroke(Color.BLACK);
														      rightShoulder37.setStrokeWidth(2.0);
														      
														      Polygon rightShoulder38 = new Polygon();
															   rightShoulder38.getPoints().addAll(new Double[]{ 
																		1207.0,689.0,
																		1214.0,683.0,
																		1215.0,682.0,
																		1212.0,635.0,
																		1220.0,639.0,
																		1221.0,667.0,
																		1223.0,685.0,
																		1224.0,686.0,
																		1223.0,687.0,
																		1218.0,694.0,
																		1217.0,694.0,
																						      });
															   Stop[] stops24 = new Stop[] { 
																         new Stop(0, Color.DARKRED),  
																         new Stop(1, Color.rgb(255, 71, 26)),
																         
																      };  
																      LinearGradient linearGradient24 = 
																         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops24);  
														      rightShoulder38.setFill(linearGradient24);
														      rightShoulder38.setStroke(Color.BLACK);
														      rightShoulder38.setStrokeWidth(2.0);
														      
														      Polygon rightShoulder39 = new Polygon();
															   rightShoulder39.getPoints().addAll(new Double[]{ 
															    		  1221.0,667.0,
															    		  1223.0,685.0,
															    		  1224.0,686.0,
															    		  1223.0,687.0,
															    		  1218.0,694.0,
															    		  1217.0,694.0,
															    		  1207.0,689.0,
															    		  1197.0,686.0,
															    		  1196.0,685.0,
															    		  1195.0,682.0,
															    		  1190.0,650.0,
															    		  1182.0,645.0,
															    		  1158.0,632.0,
															    		  1155.0,629.0,
															    		  //1158.0,632.0,
															    		  1144.0,631.0,
															    		  1141.0,629.0,
															    		  1134.0,630.0,
															    		  1140.0,687.0,
															    		  1141.0,689.0,
															    		  1203.0,880.0,
															    		  1254.0,901.0,
															    		  1255.0,901.0,
															    		  1261.0,840.0,
															    		  1241.0,680.0,
															    		  1240.0,679.0,
																				      });
															   Stop[] stops25 = new Stop[] { 
																         new Stop(0, Color.DARKRED),  
																         new Stop(1, Color.rgb(255, 71, 26)),
																         
																      };  
																      LinearGradient linearGradient25 = 
																         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops25); 	
															      rightShoulder39.setFill(linearGradient25);
															      rightShoulder39.setStroke(Color.BLACK);
															      rightShoulder39.setStrokeWidth(2.0);
															      
															      Polygon rightShoulder40 = new Polygon();
																   rightShoulder40.getPoints().addAll(new Double[]{ 
																    		  1241.0,680.0,
																    		  1240.0,679.0,
																    		  1221.0,667.0,
																    		  1223.0,685.0,
																    		  1224.0,686.0,
																    		  1223.0,685.0,
																    		  1224.0,686.0,
																    		  1223.0,687.0,
																    		  1218.0,694.0,
																    		  1217.0,694.0,
																    		  1207.0,689.0,
																    		  1197.0,686.0,
																    		  1196.0,685.0,
																    		  1195.0,682.0,
																    		  1190.0,650.0,
																    		  1182.0,645.0,
																    		  1158.0,632.0,
																    		  1155.0,629.0,
																    		  1144.0,631.0,
																    		  1141.0,629.0,
																    		  1159.0,638.0,
																    		  1160.0,639.0,
																    		  1187.0,669.0,
																    		  1188.0,670.0,
																    		  1226.0,790.0,
																    		  1227.0,790.0,
																    		  1228.0,790.0,
																    		  1224.0,692.0,
																    		  1240.0,684.0,
																					      });
																 //Instantiating the Light.Distant class
																      Light.Distant light2 = new Light.Distant(); 
																      
																      //Setting the properties of the light source 
																      light2.setAzimuth(45.0); 
																      light2.setElevation(30.0);       
																       
																      //Instantiating the Lighting class  
																      Lighting lighting2 = new Lighting(); 
																      
																      //Setting the source of the light 
																      lighting2.setLight(light2);
																      
																      rightShoulder40.setEffect(lighting2);
																      rightShoulder40.setFill(Color.YELLOW);
																      rightShoulder40.setStroke(Color.BLACK);
																      rightShoulder40.setStrokeWidth(2.0);
																      
																      Polygon rightShoulder44 = new Polygon();
																	   rightShoulder44.getPoints().addAll(new Double[]{ 
																				1144.0,636.0,
																				1145.0,637.0,
																				1146.0,638.0,
																				1147.0,656.0,
																				1146.0,657.0,
																				1145.0,657.0,
																				//1144.0,657.0,
																				1144.0,656.0,
																				//1142.0,655.0,
																				//1141.0,655.0,///
																				1140.0,638.0,
																				//1140.0,637.0,//
																				1141.0,637.0,
																				1142.0,636.0,
																								      });
																      rightShoulder44.setFill(Color.BLACK);
																      
																      Polygon rightShoulder45 = new Polygon();
																	   rightShoulder45.getPoints().addAll(new Double[]{ 
																				1146.0,659.0,
																				1147.0,659.0,
																				1148.0,661.0,
																				1151.0,683.0,
																				1149.0,685.0,
																				1147.0,685.0,
																				1146.0,685.0,
																				1144.0,660.0,
																				1145.0,659.0,
																				
																								      });
																      rightShoulder45.setFill(Color.BLACK);
																      
																      Group f =new Group (rightShoulder31,rightShoulder32,rightShoulder33,rightShoulder34,rightShoulder35,rightShoulder37,rightShoulder38,rightShoulder39,rightShoulder40,rightShoulder44,rightShoulder45);
																      
																      //Creating a rotate transition    
																      RotateTransition rotateTransition = new RotateTransition(); 
																      
																      //Setting the duration for the transition 
																      rotateTransition.setDuration(Duration.millis(30)); 
																      
																      //Setting the node for the transition 
																      rotateTransition.setNode(f);       
																      
																      //Setting the angle of the rotation 
																      rotateTransition.setByAngle(360); 
																      
																      //Setting the cycle count for the transition 
																      rotateTransition.setCycleCount(30); 
																      
																      //Setting auto reverse value to false 
																      rotateTransition.setAutoReverse(false); 
																      
																      //Playing the animation 
																      rotateTransition.play(); 
																      
																      return f;
																      
		   }
		   public Node rotate() {
			      Polygon leftShoulder16 = new Polygon();
				   leftShoulder16.getPoints().addAll(new Double[]{ 
					    	731.0,637.0,
					    	723.0,597.0,
					    	713.0,568.0,
					    	678.0,536.0,
					    	677.0,536.0,
					    	676.0,536.0,
					    	673.0,543.0,
					    	676.0,590.0,
					    	686.0,629.0,
					    	686.0,630.0,
					    	704.0,643.0,
					    	707.0,640.0,
					    	704.0,638.0,
					    	704.0,632.0,
					    	706.0,630.0,
					    	716.0,637.0,
					    	716.0,638.0,
					    	719.0,638.0,
					    	
													      });
				   Stop[] stops55 = new Stop[] { 
					         new Stop(0, Color.DARKRED),  
					         new Stop(1, Color.rgb(255, 71, 26)),
					         
					      };  
					      LinearGradient linearGradient55 = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops55); 
			      leftShoulder16.setFill(linearGradient55);
			      leftShoulder16.setStroke(Color.BLACK);
			      leftShoulder16.setStrokeWidth(2.0);
			      
			      Polygon leftShoulder17 = new Polygon();
				   leftShoulder17.getPoints().addAll(new Double[]{ 
					    	731.0,637.0,
					    	719.0,638.0,
					    	720.0,636.0,
					    	721.0,634.0,
					    	722.0,632.0,
					    	723.0,631.0,
					    	725.0,629.0,
					    	727.0,628.0,
					    	730.0,628.0,
					    	
													      });
				   Stop[] stops56 = new Stop[] { 
					         new Stop(0, Color.DARKRED),  
					         new Stop(1, Color.rgb(255, 71, 26)),
					         
					      };  
					      LinearGradient linearGradient56 = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops56); 
			      leftShoulder17.setFill(linearGradient56);
			      leftShoulder17.setStroke(Color.BLACK);
			      leftShoulder17.setStrokeWidth(2.0);
			      
			      Polygon leftShoulder18 = new Polygon();
				   leftShoulder18.getPoints().addAll(new Double[]{ 
					    	716.0,638.0,
					    	716.0,637.0,
					    	706.0,630.0,
					    	704.0,632.0,
					    	704.0,638.0,
					    	707.0,640.0,
					    	704.0,643.0,
					    	688.0,673.0,
					    	693.0,677.0,
													      });
				   Stop[] stops57 = new Stop[] { 
					         new Stop(0, Color.DARKRED),  
					         new Stop(1, Color.rgb(255, 71, 26)),
					         
					      };  
					      LinearGradient linearGradient57 = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops57);  
			      leftShoulder18.setFill(linearGradient57);
			      leftShoulder18.setStroke(Color.BLACK);
			      leftShoulder18.setStrokeWidth(2.0);
			      
			      Polygon leftShoulder19 = new Polygon();
				   
			      leftShoulder19.getPoints().addAll(new Double[]{ 
					    	704.0,643.0,
					    	674.0,620.0,
					    	673.0,620.0,
					    	672.0,620.0,
					    	642.0,672.0,
					    	614.0,848.0,
					    	653.0,871.0,
					    	690.0,802.0,
					    	684.0,796.0,
					    	682.0,798.0,
					    	681.0,798.0,
					    	672.0,790.0,
					    	672.0,755.0,
					    	682.0,733.0,
					    	677.0,727.0,
					    	673.0,711.0,
					    	693.0,677.0,
					    	688.0,673.0,
													      });
			      Stop[] stops58 = new Stop[] { 
					         new Stop(0, Color.DARKRED),  
					         new Stop(1, Color.rgb(255, 71, 26)),
					         
					      };  
					      LinearGradient linearGradient58 = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops58);  
			      leftShoulder19.setFill(linearGradient58);
			      leftShoulder19.setStroke(Color.BLACK);
			      leftShoulder19.setStrokeWidth(2.0);
			      
			      Group r =new Group (leftShoulder16,leftShoulder17,leftShoulder18,leftShoulder19);
			      
			      //Creating a rotate transition    
			      RotateTransition rotateTransition = new RotateTransition(); 
			      
			      //Setting the duration for the transition 
			      rotateTransition.setDuration(Duration.millis(30)); 
			      
			      //Setting the node for the transition 
			      rotateTransition.setNode( r);       
			      
			      //Setting the angle of the rotation 
			      rotateTransition.setByAngle(360); 
			      
			      //Setting the cycle count for the transition 
			      rotateTransition.setCycleCount(30); 
			      
			      //Setting auto reverse value to false 
			      rotateTransition.setAutoReverse(false); 
			      
			      //Playing the animation 
			      rotateTransition.play(); 
			      
			      return r;
			         
			      
		   }
		   
		   
		   public Node bodyLion() {
			   Polygon lionHeadOne = new Polygon();
			   lionHeadOne.getPoints().addAll(new Double[]{ 
			    		 805.0,580.0,
			    		 799.0,565.0,
			    		 784.0,580.0,
			    		 783.0,593.0,
			    		  
						  
														      });
		      
			   Stop[] stops70 = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient70 = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops70); 

			      lionHeadOne.setFill(linearGradient70);
			      lionHeadOne.setStroke(Color.BLACK);
			      lionHeadOne.setStrokeWidth(2.0); 
			      
			      Polygon lionHeadTwo = new Polygon();
				   lionHeadTwo.getPoints().addAll(new Double[]{ 
					    	805.0,580.0,
					    	783.0,593.0,
					    	809.0,611.0,
					    	809.0,609.0,
					    	832.0,587.0,
					    	823.0,585.0,
					    	819.0,583.0,
								  
																      });
				   Stop[] stops71 = new Stop[] { 
						   new Stop(1, Color.rgb(164, 131, 33)),  
						   new Stop(0, Color.rgb(237, 220, 114))
				   						};  
				   LinearGradient linearGradient71 = 
						   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops71);  	
				      lionHeadTwo.setFill(linearGradient71);
				      lionHeadTwo.setStroke(Color.BLACK);
				      lionHeadTwo.setStrokeWidth(2.0); 
				      
				      Polygon lionHeadThree = new Polygon();
					   lionHeadThree.getPoints().addAll(new Double[]{ 
						    	783.0,593.0,
						    	766.0,630.0,
						    	776.0,649.0,
						    	778.0,644.0,
						    	781.0,642.0,
						    	797.0,635.0,
						    	802.0,635.0,
						    	807.0,627.0,
						    	809.0,611.0,
						    	809.0,609.0,
									  
																	      });
					   Stop[] stops72 = new Stop[] { 
							   new Stop(1, Color.rgb(164, 131, 33)),  
							   new Stop(0, Color.rgb(237, 220, 114))
					   						};  
					   LinearGradient linearGradient72 = 
							   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops72);  
				      lionHeadThree.setFill(linearGradient72);
				      lionHeadThree.setStroke(Color.BLACK);
				      lionHeadThree.setStrokeWidth(2.0); 
				      
				      Polygon lionEyeBlackLeft = new Polygon();
					   lionEyeBlackLeft.getPoints().addAll(new Double[]{ 
								 807.0,615.0,
								 797.0,610.0,
								 794.0,610.0,
								 789.0,618.0,
								 789.0,622.0,
								 798.0,632.0,
								 800.0,632.0,
								 807.0,627.0,
											  
																			      });
						      lionEyeBlackLeft.setFill(Color.BLACK);
//////////////////////////////////////////////////////////////////////////////fill transition ///////////////////////////////////////////////////////////////////////////
						      Polygon lionEyeBallLeft = new Polygon();
							   lionEyeBallLeft.getPoints().addAll(new Double[]{ 
									    806.0,619.0,
									    798.0,615.0,
									    797.0,615.0,
									    794.0,618.0,
									    794.0,621.0,
									    800.0,628.0,
									    801.0,628.0,
									    806.0,624.0,
												  
																				      });
							      lionEyeBallLeft.setFill(Color.LIGHTGREEN);
							      
							      //Instantiating Fill Transition class   
							      FillTransition fill = new FillTransition();  
							        
							      //The transition will set to be auto reserved by setting this to true  
							      fill.setAutoReverse(true);  
							        
							      //setting cycle count for the fill transition   
							      fill.setCycleCount(50);  
							        
							      //setting duration for the Fill Transition   
							      fill.setDuration(Duration.millis(1000));  
							        
							      //setting the Intital from value of the color  
							      fill.setFromValue(Color.LIGHTGREEN);  
							        
							      //setting the target value of the color  
							      fill.setToValue(Color.GOLD);  
							        
							      //setting polygon as the shape onto which the fill transition will be applied   
							      fill.setShape(lionEyeBallLeft);  
							        
							      //playing the fill transition   
							      fill.play();
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////							      
							      
							    
							      Polygon lionHeadFour = new Polygon();
								   lionHeadFour.getPoints().addAll(new Double[]{ 
									    	766.0,631.0,
									    	776.0,649.0,
									    	771.0,665.0,
									    	766.0,670.0,
									    	766.0,668.0,
																				      });
								   Stop[] stops73 = new Stop[] { 
										   new Stop(1, Color.rgb(164, 131, 33)),  
										   new Stop(0, Color.rgb(237, 220, 114))
								   						};  
								   LinearGradient linearGradient73 = 
										   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops73);  
							      lionHeadFour.setFill(linearGradient73);
							      lionHeadFour.setStroke(Color.BLACK);
							      lionHeadFour.setStrokeWidth(2.0);
							      
							      Polygon lionHeadFive = new Polygon();
								   lionHeadFive.getPoints().addAll(new Double[]{ 
									    	802.0,635.0,
									    	797.0,635.0,
									    	781.0,642.0,
									    	778.0,644.0,
									    	776.0,649.0,
									    	771.0,665.0,
									    	770.0,680.0,
									    	792.0,693.0,
									    	826.0,682.0,
									    	827.0,669.0,
									    	825.0,670.0,
									    	793.0,652.0,
									    	793.0,650.0,
																				      });
								   Stop[] stops74 = new Stop[] { 
										   new Stop(1, Color.rgb(164, 131, 33)),  
										   new Stop(0, Color.rgb(237, 220, 114))
								   						};  
								   LinearGradient linearGradient74 = 
										   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops74);  
							      lionHeadFive.setFill(linearGradient74);
							      lionHeadFive.setStroke(Color.BLACK);
							      lionHeadFive.setStrokeWidth(2.0);
							      
							      Polygon lionHeadSix = new Polygon();
								   lionHeadSix.getPoints().addAll(new Double[]{ 
									    	771.0,665.0,
									    	766.0,670.0,
									    	770.0,676.0,
																				      });
								   Stop[] stops75 = new Stop[] { 
										   new Stop(1, Color.rgb(164, 131, 33)),  
										   new Stop(0, Color.rgb(237, 220, 114))
								   						};  
								   LinearGradient linearGradient75 = 
										   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops75);  
							      lionHeadSix.setFill(linearGradient75);
							      lionHeadSix.setStroke(Color.BLACK);
							      lionHeadSix.setStrokeWidth(2.0);
							      
							      Polygon lionHeadSeven = new Polygon();
								   lionHeadSeven.getPoints().addAll(new Double[]{ 
									    	783.0,688.0,
									    	779.0,694.0,
									    	778.0,694.0,
									    	777.0,694.0,
									    	776.0,693.0,
									    	772.0,683.0,
									    	770.0,680.0,
																				      });
								   Stop[] stops76 = new Stop[] { 
										   new Stop(1, Color.rgb(164, 131, 33)),  
										   new Stop(0, Color.rgb(237, 220, 114))
								   						};  
								   LinearGradient linearGradient76 = 
										   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops76); 
								   
							      lionHeadSeven.setFill(linearGradient76);
							      lionHeadSeven.setStroke(Color.BLACK);
							      lionHeadSeven.setStrokeWidth(2.0);
							      
							      Polygon lionHeadEight = new Polygon();
								   
							      lionHeadEight.getPoints().addAll(new Double[]{ 
									    	793.0,652.0,
									    	825.0,670.0,
									    	827.0,669.0,
									    	826.0,682.0,
									    	792.0,693.0,
									    	770.0,680.0,
									    	771.0,665.0,
									    	
																				      });
							      Stop[] stops77 = new Stop[] { 
										   new Stop(1, Color.rgb(164, 131, 33)),  
										   new Stop(0, Color.rgb(237, 220, 114))
								   						};  
								   LinearGradient linearGradient77 = 
										   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops77); 
							      lionHeadEight.setFill(linearGradient77);
							      lionHeadEight.setStroke(Color.BLACK);
							      lionHeadEight.setStrokeWidth(2.0);
							      
							      Polygon lionHeadNine = new Polygon();
								   lionHeadNine.getPoints().addAll(new Double[]{ 
								    		776.0,670.0,
								    		775.0,670.0,
								    		774.0,669.0,
								    		774.0,668.0,
								    		786.0,662.0,
								    		787.0,662.0,
								    		788.0,663.0,
								    		788.0,664.0,
																					      });
								      lionHeadNine.setFill(Color.BLACK);
								      
								      Polygon lionHeadTen = new Polygon();
									   lionHeadTen.getPoints().addAll(new Double[]{ 
									    		  788.0,668.0,
									    		  788.0,669.0,
									    		  788.0,670.0,
									    		  778.0,675.0,
									    		  777.0,675.0,
									    		  776.0,675.0,
									    		  775.0,674.0,
									    		  775.0,673.0,
									    		  786.0,668.0,
									    		  787.0,668.0,
										    		
																							      });
									      lionHeadTen.setFill(Color.BLACK);
								      
									      Polygon lionHead11 = new Polygon();
										   lionHead11.getPoints().addAll(new Double[]{ 
										    		 827.0,669.0,
										    		 825.0,670.0,
										    		 793.0,652.0,
										    		 802.0,635.0,
										    		 813.0,615.0,
										    		 869.0,615.0,
										    		 873.0,632.0,
										    		 859.0,652.0,
											    		
																								      });
										   Stop[] stops78 = new Stop[] { 
												   new Stop(1, Color.rgb(164, 131, 33)),  
												   new Stop(0, Color.rgb(237, 220, 114))
										   						};  
										   LinearGradient linearGradient78 = 
												   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops78); 	
										      lionHead11.setFill(linearGradient78);
										      lionHead11.setStroke(Color.BLACK);
										      lionHead11.setStrokeWidth(2.0);
										      
										      Polygon lionHead12 = new Polygon();
											   lionHead12.getPoints().addAll(new Double[]{ 
											    		807.0,627.0,
											    		809.0,611.0,
											    		809.0,609.0,
											    		844.0,578.0,
											    		870.0,578.0,
											    		871.0,580.0,
											    		872.0,581.0,
											    		905.0,581.0,
											    		907.0,579.0,
											    		922.0,579.0,
											    		927.0,585.0,
											    		927.0,586.0,
											    		927.0,587.0,
											    		885.0,612.0,
											    		875.0,632.0,
											    		875.0,633.0,
											    		874.0,633.0,
											    		873.0,632.0,
											    		869.0,615.0,
											    		814.0,615.0,
												    		
																									      });
											   Stop[] stops79 = new Stop[] { 
													   new Stop(1, Color.rgb(164, 131, 33)),  
													   new Stop(0, Color.rgb(237, 220, 114))
											   						};  
											   LinearGradient linearGradient79 = 
													   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops79);  
										      lionHead12.setFill(linearGradient79);
										      lionHead12.setStroke(Color.BLACK);
										      lionHead12.setStrokeWidth(2.0);
										      

										      Polygon lionHead13 = new Polygon();
											   lionHead13.getPoints().addAll(new Double[]{ 
												    	875.0,633.0,
												    	885.0,612.0,
												    	927.0,587.0,
												    	978.0,579.0,
												    	1000.0,597.0,
												    	1008.0,629.0,
												    	1006.0,664.0,
												    	992.0,690.0,
												    	932.0,690.0,
												    	920.0,687.0,
												    	946.0,680.0,
												    	935.0,646.0,
																										      });
											   Stop[] stops80 = new Stop[] { 
													   new Stop(1, Color.rgb(164, 131, 33)),  
													   new Stop(0, Color.rgb(237, 220, 114))
											   						};  
											   LinearGradient linearGradient80 = 
													   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops80);
											      lionHead13.setFill(linearGradient80);
											      lionHead13.setStroke(Color.BLACK);
											      lionHead13.setStrokeWidth(2.0);
											  
Polygon lionHead14 = new Polygon();
lionHead14.getPoints().addAll(new Double[]{ 
859.0,652.0,
873.0,632.0,
874.0,633.0,
875.0,633.0,
935.0,646.0,
946.0,680.0,
920.0,687.0,
900.0,686.0,
917.0,682.0,
918.0,681.0,
913.0,668.0,
911.0,664.0,
906.0,662.0,
});
Stop[] stops81 = new Stop[] { 
new Stop(1, Color.rgb(164, 131, 33)),  
new Stop(0, Color.rgb(237, 220, 114))
					};  
LinearGradient linearGradient81  = 
new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops81 ); 
lionHead14.setFill(linearGradient81 );
lionHead14.setStroke(Color.BLACK);
lionHead14.setStrokeWidth(2.0);	

Polygon lionHead15 = new Polygon();
lionHead15.getPoints().addAll(new Double[]{ 
826.0,682.0,
827.0,669.0,
859.0,652.0,
906.0,662.0,
911.0,664.0,
913.0,668.0,
918.0,681.0,
917.0,682.0,
900.0,686.0,
870.0,695.0,
869.0,695.0,
											      });
Stop[] stops82 = new Stop[] { 
new Stop(1, Color.rgb(164, 131, 33)),  
new Stop(0, Color.rgb(237, 220, 114))
			};  
LinearGradient linearGradient82 = 
new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops82);  
lionHead15.setFill(linearGradient82);
lionHead15.setStroke(Color.BLACK);
lionHead15.setStrokeWidth(2.0);

Polygon lionHead16 = new Polygon();
lionHead16.getPoints().addAll(new Double[]{ 
859.0,652.0,
827.0,669.0,
825.0,670.0,
792.0,652.0,
802.0,636.0,
848.0,636.0,
											      });
Stop[] stops83 = new Stop[] { 
new Stop(1, Color.rgb(164, 131, 33)),  
new Stop(0, Color.rgb(237, 220, 114))
			};  
LinearGradient linearGradient83 = 
new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops83); 
lionHead16.setFill(linearGradient83);
lionHead16.setStroke(Color.BLACK);
lionHead16.setStrokeWidth(2.0);

Polygon lionHead17 = new Polygon();
lionHead17.getPoints().addAll(new Double[]{ 
887.0,612.0,
927.0,587.0,
978.0,579.0,
993.0,592.0,
											      });
Stop[] stops84 = new Stop[] { 
new Stop(1, Color.rgb(164, 131, 33)),  
new Stop(0, Color.rgb(237, 220, 114))
			};  
LinearGradient linearGradient84 = 
new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops84); 
lionHead17.setFill(linearGradient84);
lionHead17.setStroke(Color.BLACK);
lionHead17.setStrokeWidth(2.0);

Polygon lionHead18 = new Polygon();
lionHead18.getPoints().addAll(new Double[]{ 
885.0,612.0,
875.0,633.0,
935.0,646.0,
938.0,653.0,
1008.0,629.0,
1000.0,597.0,
993.0,593.0,

												      });
Stop[] stops85 = new Stop[] { 
new Stop(1, Color.rgb(164, 131, 33)),  
new Stop(0, Color.rgb(237, 220, 114))
			};  
LinearGradient linearGradient85 = 
new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops85);	
lionHead18.setFill(linearGradient85);
lionHead18.setStroke(Color.BLACK);
lionHead18.setStrokeWidth(2.0);

Polygon lionHead19 = new Polygon();
lionHead19.getPoints().addAll(new Double[]{ 
938.0,653.0,
1008.0,629.0,
1006.0,664.0,
943.0,669.0,
	
													      });
Stop[] stops86 = new Stop[] { 
new Stop(1, Color.rgb(164, 131, 33)),  
new Stop(0, Color.rgb(237, 220, 114))
				};  
LinearGradient linearGradient86 = 
new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops86);	
lionHead19.setFill(linearGradient86);
lionHead19.setStroke(Color.BLACK);
lionHead19.setStrokeWidth(2.0);

Polygon lionHead20 = new Polygon();
lionHead20.getPoints().addAll(new Double[]{ 
	943.0,669.0,
	1006.0,664.0,
	992.0,690.0,
	946.0,680.0,
    	
														      });
Stop[] stops87 = new Stop[] { 
   new Stop(1, Color.rgb(164, 131, 33)),  
   new Stop(0, Color.rgb(237, 220, 114))
					};  
LinearGradient linearGradient87 = 
   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops87);	 
lionHead20.setFill(linearGradient87);
lionHead20.setStroke(Color.BLACK);
lionHead20.setStrokeWidth(2.0); 

Polygon lionHead21 = new Polygon();

lionHead21.getPoints().addAll(new Double[]{ 
	946.0,680.0,
	986.0,690.0,
	932.0,690.0,
	920.0,687.0,
    	
														      });
Stop[] stops88 = new Stop[] { 
   new Stop(1, Color.rgb(164, 131, 33)),  
   new Stop(0, Color.rgb(237, 220, 114))
					};  
LinearGradient linearGradient88 = 
   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops88);
lionHead21.setFill(linearGradient88);
lionHead21.setStroke(Color.BLACK);
lionHead21.setStrokeWidth(2.0);


Polygon lionBlackEyeRight = new Polygon();
lionBlackEyeRight.getPoints().addAll(new Double[]{ 
		893.0,616.0,
		892.0,617.0,
		886.0,629.0,
		886.0,630.0,
		918.0,639.0,
		919.0,639.0,
		920.0,639.0,
		921.0,639.0,
		941.0,625.0,
		941.0,624.0,
		941.0,622.0,
		933.0,612.0,
		932.0,611.0,
	    	
															      });
lionBlackEyeRight.setFill(Color.BLACK);

Polygon lionEyeBallRight = new Polygon();

lionEyeBallRight.getPoints().addAll(new Double[]{ 
		931.0,616.0,
		930.0,616.0,
		895.0,621.0,
		892.0,627.0,
		892.0,628.0,
		918.0,635.0,
		919.0,635.0,
		936.0,624.0,
		936.0,623.0,
		936.0,622.0,
	    	
															      });
lionEyeBallRight.setFill(Color.LIGHTGREEN);
//Instantiating Fill Transition class   
FillTransition filltwo = new FillTransition();  
  
//The transition will set to be auto reserved by setting this to true  
filltwo.setAutoReverse(true);  
  
//setting cycle count for the fill transition   
filltwo.setCycleCount(50);  
  
//setting duration for the Fill Transition   
filltwo.setDuration(Duration.millis(1000));  
  
//setting the Intital from value of the color  
filltwo.setFromValue(Color.LIGHTGREEN);  
  
//setting the target value of the color  
filltwo.setToValue(Color.GOLD);  
  
//setting polygon as the shape onto which the fill transition will be applied   
filltwo.setShape(lionEyeBallRight);  
  
//playing the fill transition   
filltwo.play();  

Polygon lionHead22 = new Polygon();
lionHead22.getPoints().addAll(new Double[]{ 
		904.0,670.0,
		905.0,669.0,
		905.0,668.0,
		904.0,667.0,
		884.0,664.0,
		882.0,665.0,
		882.0,666.0,
		883.0,667.0,
	    	
															      });
lionHead22.setFill(Color.BLACK);

Polygon lionHead23 = new Polygon();

lionHead23.getPoints().addAll(new Double[]{ 
		904.0,672.0,
		905.0,673.0,
		905.0,674.0,
		904.0,675.0,
		884.0,672.0,
		884.0,672.0,
		882.0,671.0,
		882.0,670.0,
		883.0,669.0,
	    	
															      });
lionHead23.setFill(Color.BLACK);

Polygon lionHead24 = new Polygon();
lionHead24.getPoints().addAll(new Double[]{ 
		978.0,579.0,
		993.0,592.0,
		1018.0,575.0,
		1018.0,554.0,
	    	
															      });
Stop[] stops89 = new Stop[] { 
	   new Stop(1, Color.rgb(164, 131, 33)),  
	   new Stop(0, Color.rgb(237, 220, 114))
						};  
LinearGradient linearGradient89 = 
	   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops89); 
lionHead24.setFill(linearGradient89);
lionHead24.setStroke(Color.BLACK);
lionHead24.setStrokeWidth(2.0);

Polygon lionHead25 = new Polygon();
lionHead25.getPoints().addAll(new Double[]{ 
		993.0,592.0,
		1000.0,597.0,
		1008.0,629.0,
		1032.0,620.0,
		1042.0,589.0,
		1027.0,583.0,
		1023.0,582.0,
		1018.0,583.0,
	    	
															      });
Stop[] stops90 = new Stop[] { 
	   new Stop(1, Color.rgb(164, 131, 33)),  
	   new Stop(0, Color.rgb(237, 220, 114))
						};  
LinearGradient linearGradient90 = 
	   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops90); 
lionHead25.setFill(linearGradient90);
lionHead25.setStroke(Color.BLACK);
lionHead25.setStrokeWidth(2.0);

Polygon lionHead26 = new Polygon();
lionHead26.getPoints().addAll(new Double[]{ 
		1008.0,629.0,
		1006.0,664.0,
		1030.0,657.0,
		1040.0,636.0,
		1040.0,635.0,
		1040.0,634.0,
		1031.0,623.0,
		1030.0,623.0,
	    	
															      });
Stop[] stops91 = new Stop[] { 
	   new Stop(1, Color.rgb(164, 131, 33)),  
	   new Stop(0, Color.rgb(237, 220, 114))
						};  
LinearGradient linearGradient91 = 
	   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops91);  
lionHead26.setFill(linearGradient91);
lionHead26.setStroke(Color.BLACK);
lionHead26.setStrokeWidth(2.0);

Polygon lionHead27 = new Polygon();
lionHead27.getPoints().addAll(new Double[]{ 
		1006.0,664.0,
		992.0,689.0,
		1015.0,673.0,
	    	
															      });
Stop[] stops92 = new Stop[] { 
	   new Stop(1, Color.rgb(164, 131, 33)),  
	   new Stop(0, Color.rgb(237, 220, 114))
						};  
LinearGradient linearGradient92 = 
	   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops92); 
lionHead27.setFill(linearGradient92);
lionHead27.setStroke(Color.BLACK);
lionHead27.setStrokeWidth(2.0);

Polygon lionHead28 = new Polygon();
lionHead28.getPoints().addAll(new Double[]{ 
		794.0,693.0,
		826.0,682.0,
		831.0,684.0,
		804.0,694.0,
	    	
															      });
Stop[] stops93 = new Stop[] { 
	   new Stop(1, Color.rgb(164, 131, 33)),  
	   new Stop(0, Color.rgb(237, 220, 114))
						};  
LinearGradient linearGradient93 = 
	   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops93);  
lionHead28.setFill(linearGradient93);
lionHead28.setStroke(Color.BLACK);
lionHead28.setStrokeWidth(2.0);

Polygon lionHead29 = new Polygon(); 
lionHead29.getPoints().addAll(new Double[]{ 
		782.0,688.0,
		792.0,713.0,
		802.0,706.0,
		803.0,705.0,
		804.0,694.0,
		792.0,693.0,
	    	
															      });
Stop[] stops94 = new Stop[] { 
	   new Stop(1, Color.rgb(149, 154, 157)),  
	   new Stop(0, Color.rgb(231, 231, 231))
						};  
LinearGradient linearGradient94 = 
	   new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops94);  
lionHead29.setFill(linearGradient94);
lionHead29.setStroke(Color.BLACK);
lionHead29.setStrokeWidth(2.0);

Polygon lionHead30 = new Polygon();
lionHead30.getPoints().addAll(new Double[]{ 
    	830.0,685.0,
    	830.0,690.0,
    	827.0,696.0,
    	824.0,696.0,
    	823.0,695.0,
    	823.0,693.0,
    	825.0,687.0,
    	827.0,686.0,
		    	
																      });
Stop[] stops95 = new Stop[] { 
	   new Stop(1, Color.rgb(164, 131, 33)),  
	   new Stop(0, Color.rgb(237, 220, 114))
						};  
LinearGradient linearGradient95 = 
	   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops95);	
  lionHead30.setFill(linearGradient95);
  lionHead30.setStroke(Color.BLACK);
  lionHead30.setStrokeWidth(2.0);
  
  Polygon lionHead31 = new Polygon();
   
  lionHead31.getPoints().addAll(new Double[]{ 
	    	824.0,699.0,
	    	817.0,705.0,
	    	817.0,706.0,
	    	824.0,715.0,
	    	884.0,713.0,
	    	884.0,710.0,
	    	880.0,705.0,
	    	866.0,705.0,
	    	855.0,699.0,
			    	
																	      });
  Stop[] stops96 = new Stop[] { 
		   new Stop(1, Color.rgb(164, 131, 33)),  
		   new Stop(0, Color.rgb(237, 220, 114))
   						};  
   LinearGradient linearGradient96 = 
		   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops96);
  lionHead31.setFill(linearGradient96);
  lionHead31.setStroke(Color.BLACK);
  lionHead31.setStrokeWidth(2.0);
  
  Polygon lionHead32 = new Polygon();
   lionHead32.getPoints().addAll(new Double[]{ 
	    	824.0,699.0,
	    	818.0,704.0,
	    	816.0,691.0,
			    	
																	      });
   Stop[] stops97 = new Stop[] { 
		   new Stop(1, Color.rgb(149, 154, 157)),  
		   new Stop(0, Color.rgb(231, 231, 231))
   						};  
   LinearGradient linearGradient97 = 
		   new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops97);  
  lionHead32.setFill(linearGradient97);
  lionHead32.setStroke(Color.BLACK);
  lionHead32.setStrokeWidth(2.0);
  
  Polygon lionHead33 = new Polygon();
   lionHead33.getPoints().addAll(new Double[]{ 
	    	859.0,700.0,
	    	864.0,695.0,
	    	867.0,695.0,
	    	869.0,696.0,
	    	870.0,697.0,
	    	870.0,705.0,
	    	865.0,705.0,
			    	
																	      });
   Stop[] stops98 = new Stop[] { 
		   new Stop(1, Color.rgb(149, 154, 157)),  
		   new Stop(0, Color.rgb(231, 231, 231))
   						};  
   LinearGradient linearGradient98 = 
		   new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops98); 
  lionHead33.setFill(linearGradient98);
  lionHead33.setStroke(Color.BLACK);
  lionHead33.setStrokeWidth(2.0);
  
  Polygon lionHead34 = new Polygon();
   lionHead34.getPoints().addAll(new Double[]{ 
	    	889.0,690.0,
	    	899.0,687.0,
	    	916.0,688.0,
	    	909.0,704.0,
	    	909.0,706.0,
	    	907.0,708.0,
	    	892.0,718.0,
	    	891.0,718.0,
	    	890.0,717.0,
																	      });
   Stop[] stops99 = new Stop[] { 
		   new Stop(1, Color.rgb(149, 154, 157)),  
		   new Stop(0, Color.rgb(231, 231, 231))
   						};  
   LinearGradient linearGradient99 = 
		   new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops99);  
  lionHead34.setFill(linearGradient99);
  lionHead34.setStroke(Color.BLACK);
  lionHead34.setStrokeWidth(2.0);
  
  Polygon lionHead35 = new Polygon();
   lionHead35.getPoints().addAll(new Double[]{ 
	    	884.0,696.0,
	    	877.0,704.0,
	    	877.0,705.0,
	    	880.0,705.0,
	    	885.0,712.0,
	    	887.0,712.0,
	    	890.0,709.0,
	    	889.0,696.0,
																	      });
   Stop[] stops100 = new Stop[] { 
		   new Stop(1, Color.rgb(164, 131, 33)),  
		   new Stop(0, Color.rgb(237, 220, 114))
   						};  
   LinearGradient linearGradient100 = 
		   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops100); 
  lionHead35.setFill(linearGradient100);
  lionHead35.setStroke(Color.BLACK);
  lionHead35.setStrokeWidth(2.0);
  
  Polygon lionHead36 = new Polygon();
   lionHead36.getPoints().addAll(new Double[]{ 
	    	831.0,683.0,
	    	831.0,684.0,
	    	831.0,690.0,
	    	829.0,692.0,
	    	829.0,695.0,
	    	828.0,696.0,
	    	827.0,697.0,
	    	824.0,697.0,
	    	824.0,699.0,
	    	857.0,699.0,
	    	858.0,700.0,
	    	860.0,700.0,
	    	860.0,699.0,
	    	865.0,694.0,
																	      });
  lionHead36.setFill(Color.BLACK);
  
  Polygon lionHead37 = new Polygon();
   lionHead37.getPoints().addAll(new Double[]{ 
	    	877.0,693.0,
	    	877.0,695.0,
	    	889.0,695.0,
	    	889.0,689.0,
																	      });
   Stop[] stops101 = new Stop[] { 
		   new Stop(1, Color.rgb(164, 131, 33)),  
		   new Stop(0, Color.rgb(237, 220, 114))
   						};  
   LinearGradient linearGradient101 = 
		   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops101); 
  lionHead37.setFill(linearGradient101);
  lionHead37.setStroke(Color.BLACK);
  lionHead37.setStrokeWidth(2.0);
  
  Polygon lionHead38 = new Polygon();
   lionHead38.getPoints().addAll(new Double[]{ 
	    	871.0,695.0,
	    	877.0,694.0,
	    	877.0,695.0,
	    	877.0,696.0,
	    	884.0,696.0,
	    	877.0,703.0,
	    	877.0,704.0,
	    	877.0,705.0,
	    	871.0,705.0,
																	      });
  lionHead38.setFill(Color.BLACK);
  
  
 
  

				      
				    Group l = new Group(lionHeadOne,lionHeadTwo,
				    		  lionHeadThree,lionEyeBlackLeft,lionEyeBallLeft,lionHeadFour,lionHeadFive,lionHeadSix,lionHeadSeven,lionHeadEight,lionHeadNine,lionHeadTen,lionHead11,
				    		  lionHead12,lionHead13,lionHead14,lionHead15,lionHead16,lionHead17,lionHead18,lionHead19,lionHead20,lionHead21,lionBlackEyeRight,
				    		  lionEyeBallRight,lionHead22,lionHead23,lionHead24,lionHead25,lionHead26,lionHead27,lionHead28,lionHead29,lionHead30,lionHead31,lionHead32,lionHead33,
				    		  lionHead34,lionHead35,lionHead36,lionHead37,lionHead38);
				  //Creating scale Transition 
				    ScaleTransition scaleTransition = new ScaleTransition(); 
				    
				    //Setting the duration for the transition 
				    scaleTransition.setDuration(Duration.millis(1050)); 
				    
				    //Setting the node for the transition 
				    scaleTransition.setNode(l); 
				    
				    //Setting the dimensions for scaling 
				    scaleTransition.setByY(0.1); 
				    scaleTransition.setByX(0.1); 
				    
				    //Setting the cycle count for the translation 
				    scaleTransition.setCycleCount(5000000); 
				    
				    //Setting auto reverse value to true 
				    scaleTransition.setAutoReverse(false); 
				    
				    //Playing the animation 
				    scaleTransition.play(); 
				    
				      

				 return l;     
		   }
		   
		   public Node Body() {
			   Polygon gundamBodyOne = new Polygon();
			   gundamBodyOne.getPoints().addAll(new Double[]{ 
			    		  1018.0,570.0,
			    		  1022.0,569.0,
			    		  1028.0,567.0,
			    		  1024.0,578.0,
			    		  1014.0,578.0,
			    		  1018.0,575.0,
					    	
																					      });
			   Stop[] stops102 = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient102 = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops102);
			      gundamBodyOne.setFill(linearGradient102);
			      gundamBodyOne.setStroke(Color.BLACK);
			      gundamBodyOne.setStrokeWidth(2.0);
			      
			      Polygon gundamBodyTwo = new Polygon();
				   gundamBodyTwo.getPoints().addAll(new Double[]{ 
				    		 1028.0,567.0,
				    		 1024.0,578.0,
				    		 1044.0,578.0,
				    		 1044.0,561.0,
				    		 1038.0,565.0,
						    	
																						      });
				   Stop[] stops103 = new Stop[] { 
					         new Stop(0, Color.DARKRED),  
					         new Stop(1, Color.rgb(255, 71, 26)),
					         
					      };  
					      LinearGradient linearGradient103 = 
					         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops103);
				      gundamBodyTwo.setFill(linearGradient103);
				      gundamBodyTwo.setStroke(Color.BLACK);
				      gundamBodyTwo.setStrokeWidth(2.0);
				      
				      Polygon gundamBodyThree = new Polygon();
					   gundamBodyThree.getPoints().addAll(new Double[]{ 
					    		1032.0,578.0,
					    		1030.0,584.0,
					    		1026.0,582.0,
					    		1019.0,582.0,
					    		998.0,590.0,
					    		1013.0,578.0,
							    	
																							      });
					   Stop[] stops104 = new Stop[] { 
						         new Stop(0, Color.DARKRED),  
						         new Stop(1, Color.rgb(255, 71, 26)),
						         
						      };  
						      LinearGradient linearGradient104 = 
						         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops104); 
				      gundamBodyThree.setFill(linearGradient104);
				      gundamBodyThree.setStroke(Color.BLACK);
				      gundamBodyThree.setStrokeWidth(2.0);
				      
				      Polygon gundamBodyFour = new Polygon();
					   gundamBodyFour.getPoints().addAll(new Double[]{ 
					    		1032.0,578.0,
					    		1030.0,584.0,
					    		1042.0,589.0,
					    		1042.0,593.0,
					    		1033.0,619.0,
					    		1032.0,620.0,
					    		1026.0,623.0,
					    		1030.0,623.0,
					    		1032.0,623.0,
					    		1040.0,634.0,
					    		1040.0,637.0,
					    		1031.0,657.0,
					    		1030.0,657.0,
					    		1007.0,664.0,
					    		1013.0,671.0,
					    		1048.0,671.0,
					    		1048.0,669.0,
					    		1048.0,669.0,
					    		1047.0,668.0,
					    		1045.0,578.0,
								    	
																								      });
					   Stop[] stops105 = new Stop[] { 
						         new Stop(1, Color.rgb(82, 125, 234)),  
						         new Stop(0, Color.rgb(42, 76, 162))
						      };  
						      LinearGradient linearGradient105 = 
						         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops105);	
					      gundamBodyFour.setFill(linearGradient105);
					      gundamBodyFour.setStroke(Color.BLACK);
					      gundamBodyFour.setStrokeWidth(2.0);
				      
					      Polygon gundamBodyFive = new Polygon();
						   gundamBodyFive.getPoints().addAll(new Double[]{ 
						    		920.0,687.0,
						    		917.0,689.0,
						    		913.0,695.0,
						    		913.0,696.0,
						    		992.0,693.0,
						    		1061.0,692.0,
						    		1061.0,690.0,
						    		1050.0,671.0,
						    		1015.0,671.0,
						    		991.0,689.0,
						    		929.0,690.0,
						    		
									    	
																									      });
						   Stop[] stops106 = new Stop[] { 
							         new Stop(0, Color.DARKRED),  
							         new Stop(1, Color.rgb(255, 71, 26)),
							         
							      };  
							      LinearGradient linearGradient106  = 
							         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops106 ); 
					      gundamBodyFive.setFill(linearGradient106 );
					      gundamBodyFive.setStroke(Color.BLACK);
					      gundamBodyFive.setStrokeWidth(2.0);
					      
					      Polygon gundamBodySix = new Polygon();
						   gundamBodySix.getPoints().addAll(new Double[]{ 
						    		904.0,710.0,
						    		904.0,712.0,
						    		914.0,715.0,
						    		914.0,713.0,
						    		919.0,711.0,
						    		919.0,696.0,
						    		912.0,696.0,
						    		911.0,699.0,
						    		908.0,706.0,
						    		907.0,708.0,
						    		
									    	
																									      });
						   Stop[] stops107 = new Stop[] { 
							         new Stop(1, Color.rgb(82, 125, 234)),  
							         new Stop(0, Color.rgb(42, 76, 162))
							      };  
							      LinearGradient linearGradient107 = 
							         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops107);	
					      gundamBodySix.setFill(linearGradient107);
					      gundamBodySix.setStroke(Color.BLACK);
					      gundamBodySix.setStrokeWidth(2.0);
					      
					      Polygon gundamBodySeven = new Polygon();
						   gundamBodySeven.getPoints().addAll(new Double[]{ 
						    		  919.0,696.0,
						    		  919.0,710.0,
						    		  929.0,704.0,
						    		  1033.0,710.0,
						    		  1035.0,711.0,
						    		  1036.0,713.0,
						    		  1037.0,713.0,
						    		  1037.0,710.0,
						    		  1038.0,709.0,
						    		  1052.0,705.0,
						    		  1050.0,693.0,
						    		  991.0,693.0,
						    		  
							    	
										    	
																										      });
						   Stop[] stops108 = new Stop[] { 
							         new Stop(1, Color.rgb(82, 125, 234)),  
							         new Stop(0, Color.rgb(42, 76, 162))
							      };  
							      LinearGradient linearGradient108 = 
							         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops108); 	
						      gundamBodySeven.setFill(linearGradient108);
						      gundamBodySeven.setStroke(Color.BLACK);
						      gundamBodySeven.setStrokeWidth(2.0);
						      
						      Polygon gundamBodyEight = new Polygon();
							   gundamBodyEight.getPoints().addAll(new Double[]{ 
							    		 1050.0,693.0,
							    		 1052.0,705.0,
							    		 1066.0,705.0,
							    		 1070.0,728.0,
							    		 1071.0,729.0,
							    		 1086.0,729.0,
							    		 1087.0,728.0,
							    		 1091.0,721.0,
							    		 1091.0,717.0,
							    		 1088.0,703.0,
							    		 1087.0,702.0,
							    		 1070.0,693.0,
											    	
																											      });
							   Stop[] stops109 = new Stop[] { 
								         new Stop(0, Color.DARKRED),  
								         new Stop(1, Color.rgb(255, 71, 26)),
								         
								      };  
								      LinearGradient linearGradient109 = 
								         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops109);
							      gundamBodyEight.setFill(linearGradient109);
							      gundamBodyEight.setStroke(Color.BLACK);
							      gundamBodyEight.setStrokeWidth(2.0);
							      
							      Polygon gundamBodyNine = new Polygon();
								   gundamBodyNine.getPoints().addAll(new Double[]{ 
								    		1050.0,693.0,
								    		1052.0,705.0,
								    		1066.0,705.0,
								    		1070.0,729.0,
								    		1079.0,729.0,
								    		1085.0,721.0,
								    		1085.0,717.0,
								    		1082.0,704.0,
								    		1081.0,703.0,
								    		1063.0,693.0,
												    	
																												      });
								   Stop[] stops110 = new Stop[] { 
									         new Stop(0, Color.DARKRED),  
									         new Stop(1, Color.rgb(255, 71, 26)),
									         
									      };  
									      LinearGradient linearGradient110 = 
									         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops110); 
							      gundamBodyNine.setFill(linearGradient110);
							      gundamBodyNine.setStroke(Color.BLACK);
							      gundamBodyNine.setStrokeWidth(2.0);
							      
							      Group Body =new Group(gundamBodyOne,gundamBodyTwo,gundamBodyThree,gundamBodyFour,gundamBodyFive,gundamBodySix,gundamBodySeven,
							    		  gundamBodyEight,gundamBodyNine);
							      return Body;
							      
		   }
		   public Node  ShadowBlack() {
			   Polygon ShadowBlack = new Polygon();
			   ShadowBlack.getPoints().addAll(new Double[]{ 
				    	954.0,544.0,
				    	941.0,555.0,
				    	927.0,562.0,
				    	907.0,578.0,
				    	922.0,578.0,
				    	928.0,586.0,
				    	934.0,585.0,
				    	944.0,582.0,
						    	
																				      });
			      ShadowBlack.setFill(Color.BLACK);
			      return ShadowBlack;
				
		   }
			

		   public Node gundampantsOne() {
			   Polygon gundampantsOne = new Polygon();
			   gundampantsOne.getPoints().addAll(new Double[]{ 
				    	792.0,713.0,
				    	787.0,713.0,
				    	778.0,720.0,
				    	837.0,716.0,
				    	837.0,715.0,
				    	824.0,715.0,
				    	819.0,710.0,
				    	
								    	
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);		
			      gundampantsOne.setFill(linearGradient);
			      gundampantsOne.setStroke(Color.BLACK);
			      gundampantsOne.setStrokeWidth(2.0);
			      return gundampantsOne;
		   }
		   public Node gundampantsTwo() {
			   Polygon gundampantsTwo = new Polygon();
			   gundampantsTwo.getPoints().addAll(new Double[]{ 
						  838.0,716.0,
						  825.0,734.0,
						  825.0,737.0,
						  829.0,747.0,
						  828.0,760.0,
						  795.0,760.0,
						  791.0,765.0,
						  785.0,789.0,
						  783.0,789.0,
						  760.0,763.0,
						  760.0,762.0,
						  760.0,761.0,
						  777.0,721.0,
						    	
										    	
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);		
				      gundampantsTwo.setFill(linearGradient);
				      gundampantsTwo.setStroke(Color.BLACK);
				      gundampantsTwo.setStrokeWidth(2.0);
					  return gundampantsTwo;    
			   
		   }
		   public Node gundampantsThree() {
			   Polygon gundampantsThree = new Polygon();
			   gundampantsThree.getPoints().addAll(new Double[]{ 
						 760.0,763.0,
						 785.0,789.0,
						 781.0,801.0,
						 782.0,813.0,
						 760.0,782.0,
										    	
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);	
			      gundampantsThree.setFill(linearGradient);
			      gundampantsThree.setStroke(Color.BLACK);
			      gundampantsThree.setStrokeWidth(2.0);
			      return gundampantsThree;
			   
		   }
		   public Node gundampantsFour() {
			   Polygon gundampantsFour = new Polygon();
			   gundampantsFour.getPoints().addAll(new Double[]{ 
						 828.0,760.0,
						 795.0,760.0,
						 791.0,765.0,
						 785.0,789.0,
						 781.0,801.0,
						 782.0,813.0,
						 787.0,835.0,
						 820.0,854.0,
						 819.0,835.0,
						 817.0,830.0,
						 817.0,814.0,
						 822.0,798.0,
										    	
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);	 
		      gundampantsFour.setFill(linearGradient);
		      gundampantsFour.setStroke(Color.BLACK);
		      gundampantsFour.setStrokeWidth(2.0);
		      return gundampantsFour;
		   }
		   public Node gundampantsFive() {
			   Polygon gundampantsFive = new Polygon();
			   gundampantsFive.getPoints().addAll(new Double[]{ 
						 767.0,776.0,
						 766.0,776.0,
						 766.0,784.0,
						 780.0,804.0,
						 780.0,792.0,
										    	
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);	 
		      gundampantsFive.setFill(linearGradient);
		      gundampantsFive.setStroke(Color.BLACK);
		      gundampantsFive.setStrokeWidth(2.0);
		      return gundampantsFive;
		   }
		   public Node gundampantsSix() {
			   Polygon gundampantsSix = new Polygon();
			   gundampantsSix.getPoints().addAll(new Double[]{ 
						 838.0,715.0,
						 825.0,734.0,
						 825.0,737.0,
						 829.0,747.0,
						 829.0,748.0,
						 874.0,748.0,
						 903.0,714.0,
						 903.0,712.0,
						 903.0,711.0,
						 902.0,711.0,
						 901.0,711.0,
						 892.0,718.0,
						 891.0,718.0,
						 890.0,717.0,
						 890.0,713.0,
						 889.0,712.0,
						 886.0,713.0,
										    	
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);   
		      gundampantsSix.setFill(linearGradient);
		      gundampantsSix.setStroke(Color.BLACK);
		      gundampantsSix.setStrokeWidth(2.0);
		      return gundampantsSix;
			   
		   }
		   public Node gundampantsSeven() {
			   Polygon gundampantsSeven = new Polygon();
			   gundampantsSeven.getPoints().addAll(new Double[]{ 
						838.0,715.0,
						825.0,734.0,
						825.0,737.0,
						866.0,737.0,
						886.0,713.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);    
		      gundampantsSeven.setFill(linearGradient);
		      gundampantsSeven.setStroke(Color.BLACK);
		      gundampantsSeven.setStrokeWidth(2.0);
		      return gundampantsSeven;
			   
		   }
		   public Node gundampantsEight() {
			   Polygon gundampantsEight = new Polygon();
			   gundampantsEight.getPoints().addAll(new Double[]{ 
						850.0,715.0,
						839.0,737.0,
						866.0,737.0,
						884.0,714.0,
																										      });
		      gundampantsEight.setFill(Color.BLACK);
		      return gundampantsEight;
			   
		   }
		   public Node gundampantsNine() {
			   Polygon gundampantsNine = new Polygon();
			   gundampantsNine.getPoints().addAll(new Double[]{ 
						829.0,748.0,
						874.0,748.0,
						870.0,801.0,
						822.0,801.0,
																										      });
			   
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
		      gundampantsNine.setFill(linearGradient);
		      gundampantsNine.setStroke(Color.BLACK);
		      gundampantsNine.setStrokeWidth(2.0);
		      return gundampantsNine;
		   }
		   public Node gundampantsTen() {
			   Polygon gundampantsTen = new Polygon();
			   gundampantsTen.getPoints().addAll(new Double[]{ 
						822.0,801.0,
						819.0,810.0,
						819.0,813.0,
						838.0,838.0,
						888.0,840.0,
						897.0,831.0,
						871.0,801.0,
						
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);   
		      gundampantsTen.setFill(linearGradient);
		      gundampantsTen.setStroke(Color.BLACK);
		      gundampantsTen.setStrokeWidth(2.0);
		      return gundampantsTen;
			   
			   
		   }
		   public Node gundampants11() {
			   Polygon gundampants11 = new Polygon();
			   gundampants11.getPoints().addAll(new Double[]{ 
						819.0,813.0,
						838.0,838.0,
						887.0,840.0,
						866.0,813.0,
																										      });
			   
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);
		      gundampants11.setFill(linearGradient);
		      gundampants11.setStroke(Color.BLACK);
		      gundampants11.setStrokeWidth(2.0);
		      return gundampants11;
			   
		   }
		   public Node gundampants12() {
			   Polygon gundampants12 = new Polygon();
			   gundampants12.getPoints().addAll(new Double[]{ 
						866.0,813.0,
						878.0,828.0,
						845.0,828.0,
						835.0,813.0,
																										      });
		      gundampants12.setFill(Color.BLACK);
		      return gundampants12;
		   }
		   public Node gundampants13() {
			   Polygon gundampants13 = new Polygon();
			   gundampants13.getPoints().addAll(new Double[]{ 
						819.0,813.0,
						817.0,814.0,
						817.0,828.0,
						819.0,830.0,
						820.0,853.0,
						831.0,829.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      gundampants13.setFill(linearGradient);
		      gundampants13.setStroke(Color.BLACK);
		      gundampants13.setStrokeWidth(2.0);
		      return gundampants13;
			   
		   }
		   public Node gundampants14() {
			   Polygon gundampants14 = new Polygon();
			   gundampants14.getPoints().addAll(new Double[]{ 
						903.0,713.0,
						874.0,748.0,
						871.0,801.0,
						897.0,831.0,
						898.0,831.0,
						893.0,817.0,
						893.0,810.0,
						900.0,765.0,
						905.0,761.0,
						915.0,715.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      gundampants14.setFill(linearGradient);
		      gundampants14.setStroke(Color.BLACK);
		      gundampants14.setStrokeWidth(2.0);
		      return gundampants14 ;
		      
		   }
		   public Node gundampants15() {
			   Polygon gundampants15 = new Polygon();
			   gundampants15.getPoints().addAll(new Double[]{ 
						915.0,715.0,
						905.0,761.0,
						946.0,761.0,
						945.0,799.0,
						960.0,831.0,
						1046.0,784.0,
						1046.0,771.0,
						1034.0,729.0,
						1034.0,724.0,
						1037.0,715.0,
						1036.0,713.0,
						1033.0,710.0,
						929.0,704.0,
						916.0,712.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      gundampants15.setFill(linearGradient);
		      gundampants15.setStroke(Color.BLACK);
		      gundampants15.setStrokeWidth(2.0);
		      return gundampants15;
		      
			   
		   }
		   public Node gundampants16() {
			   Polygon gundampants16 = new Polygon();
			   gundampants16.getPoints().addAll(new Double[]{ 
						905.0,761.0,
						900.0,766.0,
						893.0,811.0,
						893.0,816.0,
						907.0,859.0,
						909.0,859.0,
						953.0,843.0,
						961.0,832.0,
						960.0,830.0,
						945.0,799.0,
						946.0,761.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      gundampants16.setFill(linearGradient);
		      gundampants16.setStroke(Color.BLACK);
		      gundampants16.setStrokeWidth(2.0);
		      return gundampants16;
			   
		   }
		   public Node gundampants17() {
			   Polygon gundampants17 = new Polygon();
			   gundampants17.getPoints().addAll(new Double[]{ 
						946.0,762.0,
						941.0,765.0,
						939.0,767.0,
						938.0,795.0,
						936.0,809.0,
						953.0,843.0,
						961.0,832.0,
						960.0,830.0,
						945.0,799.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      gundampants17.setFill(linearGradient);
		      gundampants17.setStroke(Color.BLACK);
		      gundampants17.setStrokeWidth(2.0);
		      return gundampants17;
		   }
		   public Node gundampants18() {
			   Polygon gundampants18 = new Polygon();
			   gundampants18.getPoints().addAll(new Double[]{ 
						916.0,712.0,
						915.0,715.0,
						905.0,761.0,
						946.0,761.0,
						945.0,799.0,
						1022.0,767.0,
						1018.0,721.0,
						1017.0,720.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      gundampants18.setFill(linearGradient);
		      gundampants18.setStroke(Color.BLACK);
		      gundampants18.setStrokeWidth(2.0);
		      return gundampants18;
		   }
		   public Node gundampants19() {
			   Polygon gundampants19 = new Polygon();
			   gundampants19.getPoints().addAll(new Double[]{ 
						956.0,804.0,
						956.0,801.0,
						1014.0,775.0,
						1015.0,775.0,
						1016.0,775.0,
						1024.0,789.0,
						1024.0,791.0,
						967.0,820.0,
						964.0,820.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      gundampants19.setFill(linearGradient);
		      gundampants19.setStroke(Color.BLACK);
		      gundampants19.setStrokeWidth(2.0);
		      return gundampants19;
		   }
		   public Node gundampants20() {
			   Polygon gundampants20 = new Polygon();
			   gundampants20.getPoints().addAll(new Double[]{ 
						1014.0,775.0,
						1015.0,775.0,
						1020.0,783.0,
						972.0,807.0,
						971.0,807.0,
						970.0,806.0,
						968.0,796.0,
																										      });
		      gundampants20.setFill(Color.BLACK);
		      return gundampants20;
		   }
		   public Node gundampants21() {
			   Polygon gundampants21 = new Polygon();
			   gundampants21.getPoints().addAll(new Double[]{ 
						831.0,829.0,
						820.0,853.0,
						845.0,862.0,
						858.0,864.0,
						876.0,866.0,
						917.0,868.0,
						921.0,855.0,
						907.0,859.0,
						897.0,832.0,
						888.0,840.0,
						838.0,838.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      gundampants21.setFill(linearGradient);
		      gundampants21.setStroke(Color.BLACK);
		      gundampants21.setStrokeWidth(2.0);
		      return gundampants21;
			   
		   }
		   public Node gundampants22() {
			   Polygon gundampants22 = new Polygon();
			   gundampants22.getPoints().addAll(new Double[]{ 
						921.0,854.0,
						918.0,865.0,
						924.0,865.0,
						928.0,852.0,
																										      });
				//Instantiating the Light.Distant class
			      Light.Distant light = new Light.Distant(); 
			      
			      //Setting the properties of the light source 
			      light.setAzimuth(45.0); 
			      light.setElevation(30.0);       
			       
			      //Instantiating the Lighting class  
			      Lighting lighting = new Lighting(); 
			      
			      //Setting the source of the light 
			      lighting.setLight(light);
			      
			      gundampants22.setEffect(lighting);
		      gundampants22.setFill(Color.YELLOW);
		      gundampants22.setStroke(Color.BLACK);
		      gundampants22.setStrokeWidth(2.0);
		      return gundampants22;
		   }
		   public Node gundampants23() {
			   Polygon gundampants23 = new Polygon();
			   gundampants23.getPoints().addAll(new Double[]{ 
						1005.0,693.0,
						1012.0,709.0,
						1033.0,710.0,
						1036.0,713.0,
						1037.0,715.0,
						1037.0,710.0,
						1038.0,709.0,
						1052.0,705.0,
						1050.0,693.0,
			   });		
						 Stop[] stops = new Stop[] { 
						         new Stop(1, Color.rgb(82, 125, 234)),  
						         new Stop(0, Color.rgb(42, 76, 162))
						      };  
						      LinearGradient linearGradient = 
						         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  																							    
						      	gundampants23.setFill(linearGradient);
						      	gundampants23.setStroke(Color.BLACK);
						      	gundampants23.setStrokeWidth(2.0);
						      	return gundampants23;
			   
				}
		   public Node gundampants24() {
			   Polygon gundampants24 = new Polygon();
			   gundampants24.getPoints().addAll(new Double[]{ 
						1006.0,692.0,
						1015.0,672.0,
						1050.0,672.0,
						1061.0,690.0,
						1061.0,692.0,
						
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
		      gundampants24.setFill(linearGradient);
		      gundampants24.setStroke(Color.BLACK);
		      gundampants24.setStrokeWidth(2.0);
		      return gundampants24;
			   
		   }
		   public Node gundampants25() {
			   Polygon gundampants25 = new Polygon();
			   gundampants25.getPoints().addAll(new Double[]{ 
						1063.0,691.0,
						1079.0,682.0,
						1070.0,692.0,
						1063.0,692.0,
						
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      gundampants25.setFill(linearGradient);
		      gundampants25.setStroke(Color.BLACK);
		      gundampants25.setStrokeWidth(2.0);
		      return gundampants25;
		   }
		   public Node gundampants26() {
			   Polygon gundampants26 = new Polygon();
			   gundampants26.getPoints().addAll(new Double[]{ 
						1079.0,682.0,
						1070.0,692.0,
						1074.0,695.0,
						1085.0,696.0,
						1093.0,685.0,
						1094.0,674.0,
						
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      gundampants26.setFill(linearGradient);
		      gundampants26.setStroke(Color.BLACK);
		      gundampants26.setStrokeWidth(2.0);
		      return gundampants26;
			   
		   }
		   public Node gundamLeftLegOne() {
			   Polygon gundamLeftLegOne = new Polygon();
			   gundamLeftLegOne.getPoints().addAll(new Double[]{ 
						759.0,761.0,
						750.0,750.0,
						728.0,774.0,
						743.0,767.0,
						759.0,788.0,
						763.0,789.0,
						765.0,792.0,
						768.0,800.0,
						769.0,800.0,
						771.0,796.0,
						760.0,782.0,
						
																										      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops); 
		      gundamLeftLegOne.setFill(linearGradient);
		      gundamLeftLegOne.setStroke(Color.BLACK);
		      gundamLeftLegOne.setStrokeWidth(2.0);
		      return gundamLeftLegOne;
			   
		   }
		   public Node gundampants27() {
			   Polygon gundampants27 = new Polygon();
			   gundampants27.getPoints().addAll(new Double[]{ 
						771.0,796.0,
						769.0,800.0,
						770.0,809.0,
						777.0,826.0,
						787.0,835.0,
						781.0,812.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      gundampants27.setFill(linearGradient);
		      gundampants27.setStroke(Color.BLACK);
		      gundampants27.setStrokeWidth(2.0);
		      return gundampants27;
		   }
		   public Node gundamLeftLegTwo() {
			   Polygon gundamLeftLegTwo = new Polygon();
			   gundamLeftLegTwo.getPoints().addAll(new Double[]{ 
						737.0,770.0,
						743.0,767.0,
						759.0,788.0,
						757.0,791.0,
						755.0,792.0,
																										      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);  
		      gundamLeftLegTwo.setFill(linearGradient);
		      gundamLeftLegTwo.setStroke(Color.BLACK);
		      gundamLeftLegTwo.setStrokeWidth(2.0);
		      return gundamLeftLegTwo;
		   }
		   public Node gundamLeftLegThree() {
			   Polygon gundamLeftLegThree = new Polygon();
			    gundamLeftLegThree.getPoints().addAll(new Double[]{ 
						747.0,782.0,
						740.0,787.0,
						740.0,788.0,
						750.0,819.0,
						757.0,824.0,
						761.0,821.0,
						751.0,796.0,
						751.0,795.0,
						755.0,792.0,
			    });
			    Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
						   
		      gundamLeftLegThree.setFill(linearGradient);
		      gundamLeftLegThree.setStroke(Color.BLACK);
		      gundamLeftLegThree.setStrokeWidth(2.0);
		      return gundamLeftLegThree;
		   }
		   public Node gundamLeftLegFour() {
			   Polygon gundamLeftLegFour = new Polygon();
			   gundamLeftLegFour.getPoints().addAll(new Double[]{ 
						759.0,788.0,
						765.0,792.0,
						768.0,800.0,
						770.0,809.0,
						777.0,826.0,
						777.0,829.0,
						770.0,835.0,
						769.0,835.0,
						763.0,829.0,
						752.0,796.0,
						755.0,792.0,
						757.0,791.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      gundamLeftLegFour.setFill(linearGradient);
		      gundamLeftLegFour.setStroke(Color.BLACK);
		      gundamLeftLegFour.setStrokeWidth(2.0);
		      return gundamLeftLegFour; 
		   }
		   public Node gundamLeftLegFive() {
			   Polygon gundamLeftLegFive = new Polygon();
			   gundamLeftLegFive.getPoints().addAll(new Double[]{ 
						740.0,787.0,
						740.0,788.0,
						750.0,819.0,
						756.0,823.0,
						746.0,791.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      gundamLeftLegFive.setFill(linearGradient);
		      gundamLeftLegFive.setStroke(Color.BLACK);
		      gundamLeftLegFive.setStrokeWidth(2.0);
		      return gundamLeftLegFive;
			   
		   }
		   public Node gundamLeftLegSix() {
			   Polygon gundamLeftLegSix = new Polygon();
			   gundamLeftLegSix.getPoints().addAll(new Double[]{ 
						752.0,796.0,
						763.0,829.0,
						769.0,835.0,
						770.0,835.0,
						758.0,798.0,
																										      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.DARKRED),  
				         new Stop(1, Color.rgb(255, 71, 26)),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);  
		      gundamLeftLegSix.setFill(linearGradient);
		      gundamLeftLegSix.setStroke(Color.BLACK);
		      gundamLeftLegSix.setStrokeWidth(2.0);
		      return gundamLeftLegSix;
		   }
		   public Node gundamLeftLegSeven() {
			   Polygon gundamLeftLegSeven = new Polygon();
			   gundamLeftLegSeven.getPoints().addAll(new Double[]{ 
						760.0,821.0,
						736.0,838.0,
						736.0,839.0,
						736.0,840.0,
						740.0,844.0,
						741.0,844.0,
						742.0,844.0,
						763.0,829.0,
																										      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops); 
		      gundamLeftLegSeven.setFill(linearGradient);
		      gundamLeftLegSeven.setStroke(Color.BLACK);
		      gundamLeftLegSeven.setStrokeWidth(2.0);
		      return gundamLeftLegSeven;
			   
		   }
		   public Node gundamLeftLegeight() {
			   Polygon gundamLeftLegeight = new Polygon();
			   gundamLeftLegeight.getPoints().addAll(new Double[]{ 
			    		763.0,829.0,
			    		769.0,835.0,
			    		770.0,835.0,
			    		777.0,829.0,
			    		777.0,838.0,
			    		764.0,846.0,
			    		764.0,841.0,
			    		762.0,837.0,
			    		760.0,835.0,
			    		757.0,835.0,
			    		755.0,835.0,
			    		
																											      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops); 	
			      gundamLeftLegeight.setFill(linearGradient);
			      gundamLeftLegeight.setStroke(Color.BLACK);
			      gundamLeftLegeight.setStrokeWidth(2.0);
			      return gundamLeftLegeight;
			   
		   }
		   public Node gundamLeftLegnine() {
			   Polygon gundamLeftLegnine = new Polygon();
			   gundamLeftLegnine.getPoints().addAll(new Double[]{ 
			    		764.0,846.0,
			    		764.0,841.0,
			    		762.0,837.0,
			    		760.0,835.0,
			    		757.0,835.0,
			    		755.0,835.0,
			    		742.0,844.0,
			    		741.0,844.0,
			    		740.0,844.0,
			    		736.0,840.0,
			    		736.0,839.0,
			    		736.0,838.0,
			    		747.0,830.0,
			    		745.0,829.0,
			    		739.0,829.0,
			    		721.0,837.0,
			    		721.0,838.0,
			    		738.0,850.0,
			    		736.0,871.0,
			    		719.0,863.0,
			    		736.0,876.0,
			    		761.0,852.0,
			    		763.0,849.0,
			    		
																											      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLegnine.setFill(linearGradient);
			   gundamLeftLegnine.setStroke(Color.BLACK);
			   gundamLeftLegnine.setStrokeWidth(2.0);
			      return gundamLeftLegnine;
			   
		   }
		   public Node gundamLeftLegTen() {
			   Polygon gundamLeftLegTen = new Polygon();
			   gundamLeftLegTen.getPoints().addAll(new Double[]{ 
			    		738.0,850.0,
			    		736.0,871.0,
			    		701.0,856.0,
			    		697.0,848.0,
			    		697.0,845.0,
			    		708.0,827.0,
			    		710.0,825.0,
			    		714.0,831.0,
			    		714.0,843.0,
			    		730.0,843.0,
			    		
																											      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLegTen.setFill(linearGradient);
			   gundamLeftLegTen.setStroke(Color.BLACK);
			   gundamLeftLegTen.setStrokeWidth(2.0);
			      return gundamLeftLegTen;
			   
		   }
		   public Node gundamLeftLeg11() {
			   Polygon gundamLeftLeg11 = new Polygon();
			   gundamLeftLeg11.getPoints().addAll(new Double[]{ 
			    		701.0,856.0,
			    		697.0,848.0,
			    		697.0,845.0,
			    		708.0,827.0,
			    		710.0,825.0,
			    		714.0,831.0,
			    		
																											      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg11.setFill(linearGradient);
			   gundamLeftLeg11.setStroke(Color.BLACK);
			   gundamLeftLeg11.setStrokeWidth(2.0);
			      return gundamLeftLeg11;
		   }
		   public Node gundamLeftLeg12() {
			   Polygon gundamLeftLeg12 = new Polygon();
			   gundamLeftLeg12.getPoints().addAll(new Double[]{ 
			    		714.0,832.0,
			    		714.0,848.0,
			    		738.0,850.0,
			    		736.0,871.0,
			    		701.0,856.0,
			    		
																											      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg12.setFill(linearGradient);
			   gundamLeftLeg12.setStroke(Color.BLACK);
			   gundamLeftLeg12.setStrokeWidth(2.0);
			      return gundamLeftLeg12;
		   }
		   public Node gundamLeftLeg13() {
			   Polygon gundamLeftLeg13 = new Polygon();
			   gundamLeftLeg13.getPoints().addAll(new Double[]{ 
			    		698.0,844.0,
			    		694.0,838.0,
			    		694.0,837.0,
			    		707.0,817.0,
			    		708.0,817.0,
			    		711.0,823.0,
			    		
																											      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg13.setFill(linearGradient);
			   gundamLeftLeg13.setStroke(Color.BLACK);
			   gundamLeftLeg13.setStrokeWidth(2.0);
			      return gundamLeftLeg13;
		   }
		   public Node gundamLeftLeg14() {
			   Polygon gundamLeftLeg14 = new Polygon();
			   gundamLeftLeg14.getPoints().addAll(new Double[]{ 
			    		721.0,837.0,
			    		728.0,843.0,
			    		714.0,843.0,
			    		714.0,837.0,
			    		
																											      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg14.setFill(linearGradient);
			   gundamLeftLeg14.setStroke(Color.BLACK);
			   gundamLeftLeg14.setStrokeWidth(2.0);
			      return gundamLeftLeg14;
			   
		   }
		   public Node gundamLeftLeg15() {
			   Polygon gundamLeftLeg15 = new Polygon();
			   gundamLeftLeg15.getPoints().addAll(new Double[]{ 
			    	760.0,844.0,
			    	756.0,840.0,
			    	754.0,840.0,
			    	749.0,845.0,
			    	749.0,849.0,
			    	753.0,853.0,
			    	756.0,853.0,
			    	760.0,849.0,
																											      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg15.setFill(linearGradient);
			   gundamLeftLeg15.setStroke(Color.BLACK);
			   gundamLeftLeg15.setStrokeWidth(2.0);
			      return gundamLeftLeg15;
			   
		   }
		   public Node gundamLeftLeg16() {
			   Polygon gundamLeftLeg16 = new Polygon();
			   gundamLeftLeg16.getPoints().addAll(new Double[]{ 
				    	778.0,838.0,
				    	764.0,846.0,
				    	763.0,849.0,
				    	761.0,852.0,
				    	764.0,856.0,
				    	764.0,862.0,
				    	769.0,862.0,
				    	778.0,846.0,
																												      });
			   gundamLeftLeg16.setFill(Color.BLACK);
			   
				      return gundamLeftLeg16;
		   }
		   public Node gundamLeftLeg17() {
			   Polygon gundamLeftLeg17=new Polygon();
			   gundamLeftLeg17.getPoints().addAll(new Double[]{ 
				    	761.0,852.0,
				    	736.0,876.0,
				    	719.0,864.0,
				    	717.0,864.0,
				    	710.0,876.0,
				    	710.0,879.0,
				    	728.0,884.0,
				    	730.0,884.0,
				    	764.0,862.0,
				    	764.0,856.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);	
			   gundamLeftLeg17.setFill(linearGradient);
			   gundamLeftLeg17.setStroke(Color.BLACK);
			   gundamLeftLeg17.setStrokeWidth(2.0);
				      return gundamLeftLeg17;
			   
		   }
		   public Node gundamLeftLeg18() {
			   Polygon gundamLeftLeg18=new Polygon();
			   gundamLeftLeg18.getPoints().addAll(new Double[]{ 
				    	764.0,862.0,
				    	730.0,884.0,
				    	728.0,884.0,
				    	710.0,879.0,
				    	710.0,876.0,
				    	715.0,866.0,//
				    	695.0,887.0,
				    	732.0,896.0,
				    	772.0,958.0,
				    	774.0,958.0,
				    	800.0,941.0,
				    	793.0,937.0,
				    	787.0,932.0,
				    	782.0,927.0,
				    	781.0,927.0,
				    	776.0,931.0,
				    	768.0,931.0,
				    	743.0,888.0,
				    	743.0,886.0,
				    	769.0,862.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);	
			   gundamLeftLeg18.setFill(linearGradient);
			   gundamLeftLeg18.setStroke(Color.BLACK);
			   gundamLeftLeg18.setStrokeWidth(2.0);
			   return gundamLeftLeg18;
			   
			   
		   }
		   public Node gundamLeftLeg19() {
			   Polygon gundamLeftLeg19=new Polygon();
			   gundamLeftLeg19.getPoints().addAll(new Double[]{ 
				    	769.0,862.0,
				    	743.0,886.0,
				    	743.0,888.0,
				    	768.0,931.0,
				    	776.0,931.0,
				    	781.0,927.0,
				    	782.0,927.0,
				    	775.0,919.0,
				    	771.0,913.0,
				    	766.0,905.0,
				    	762.0,896.0,
				    	757.0,885.0,
				    	757.0,883.0,
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg19.setFill(linearGradient);
			   gundamLeftLeg19.setStroke(Color.BLACK);
			   gundamLeftLeg19.setStrokeWidth(2.0);
			   return gundamLeftLeg19;
			   
		   }
		   public Node gundamLeftLeg20() {
			   Polygon gundamLeftLeg20 = new Polygon();
			   gundamLeftLeg20.getPoints().addAll(new Double[]{ 
				    	768.0,931.0,
				    	776.0,931.0,
				    	752.0,891.0,
				    	743.0,886.0,
				    	743.0,888.0,
				    	
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg20.setFill(linearGradient);
			   gundamLeftLeg20.setStroke(Color.BLACK);
			   gundamLeftLeg20.setStrokeWidth(2.0);
			   return gundamLeftLeg20;
			   
		   }
		   public Node gundamLeftLeg21() {
			   Polygon gundamLeftLeg21=new Polygon();
			   gundamLeftLeg21.getPoints().addAll(new Double[]{ 
				    	769.0,862.0,
				    	756.0,875.0,
				    	759.0,876.0,
				    	761.0,876.0,
				    	   	
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops); 
			   gundamLeftLeg21.setFill(linearGradient);
			   gundamLeftLeg21.setStroke(Color.BLACK);
			   gundamLeftLeg21.setStrokeWidth(2.0);
			   return gundamLeftLeg21;
		   }
		   public Node gundamLeftLeg22() {
			   Polygon gundamLeftLeg22=new Polygon();
			   gundamLeftLeg22.getPoints().addAll(new Double[]{ 
				    	777.0,829.0,
				    	777.0,838.0,
				    	776.0,846.0,
				    	769.0,862.0,
				    	757.0,883.0,
				    	757.0,885.0,
				    	762.0,896.0,
				    	766.0,905.0,
				    	771.0,913.0,
				    	775.0,919.0,
				    	782.0,927.0,
				    	787.0,932.0,
				    	793.0,937.0,
				    	800.0,941.0,
				    	811.0,946.0,
				    	818.0,948.0,
				    	825.0,948.0,
				    	834.0,948.0,
				    	845.0,862.0,
				    	820.0,853.0,
				    	787.0,835.0,
				    	780.0,829.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg22.setFill(linearGradient);
			   gundamLeftLeg22.setStroke(Color.BLACK);
			   gundamLeftLeg22.setStrokeWidth(2.0);
			   return gundamLeftLeg22;
		   }
		   public Node gundamLeftLeg23() {
			   Polygon gundamLeftLeg23=new Polygon();
			   gundamLeftLeg23.getPoints().addAll(new Double[]{ 
				    	787.0,835.0,
				    	787.0,851.0,
				    	769.0,888.0,
				    	769.0,892.0,
				    	772.0,897.0,
				    	775.0,905.0,
				    	779.0,913.0,
				    	783.0,918.0,
				    	788.0,924.0,
				    	793.0,929.0,
				    	799.0,934.0,
				    	807.0,938.0,
				    	816.0,942.0,
				    	825.0,945.0,
				    	834.0,948.0,
				    	845.0,862.0,
				    	820.0,853.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg23.setFill(linearGradient);
			   gundamLeftLeg23.setStroke(Color.BLACK);
			   gundamLeftLeg23.setStrokeWidth(2.0);
			   return gundamLeftLeg23;
		   }
		   public Node gundamLeftLeg24() {
			   Polygon gundamLeftLeg24=new Polygon();
			   gundamLeftLeg24.getPoints().addAll(new Double[]{ 
				    	845.0,862.0,
				    	836.0,928.0,
				    	839.0,933.0,
				    	848.0,933.0,
				    	855.0,927.0,
				    	860.0,865.0,
				    	858.0,864.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg24.setFill(linearGradient);
			   gundamLeftLeg24.setStroke(Color.BLACK);
			   gundamLeftLeg24.setStrokeWidth(2.0);
			   return gundamLeftLeg24;
		   }
		   public Node gundamLeftLeg25() {
			   Polygon gundamLeftLeg25 = new Polygon(); 
			   gundamLeftLeg25.getPoints().addAll(new Double[]{ 
				    	857.0,865.0,
				    	852.0,919.0,
				    	852.0,920.0,
				    	848.0,924.0,
				    	844.0,924.0,
				    	841.0,921.0,
				    	840.0,920.0,
				    	840.0,918.0,
				    	848.0,863.0,
																												      });
			   gundamLeftLeg25.setFill(Color.BLACK);
			   return gundamLeftLeg25;
			   
		   }
		   public Node gundamLeftLet26() {
			   Polygon gundamLeftLet26 = new Polygon();
			   gundamLeftLet26.getPoints().addAll(new Double[]{ 
				    	860.0,865.0,
				    	854.0,947.0,
				    	870.0,943.0,
				    	878.0,939.0,
				    	885.0,935.0,
				    	892.0,930.0,
				    	901.0,924.0,
				    	906.0,920.0,
				    	912.0,914.0,
				    	915.0,909.0,
				    	918.0,902.0,
				    	922.0,894.0,
				    	923.0,893.0,
				    	923.0,891.0,
				    	913.0,868.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLet26.setFill(linearGradient);
			   gundamLeftLet26.setStroke(Color.BLACK);
			   gundamLeftLet26.setStrokeWidth(2.0);
			   return gundamLeftLet26;
		   }
		   public Node gundamLeftLeg27() {
			   Polygon gundamLeftLeg27=new Polygon();
			   gundamLeftLeg27.getPoints().addAll(new Double[]{ 
				    	854.0,947.0,
				    	849.0,949.0,
				    	846.0,949.0,
				    	845.0,948.0,
				    	846.0,934.0,
				    	848.0,934.0,
				    	855.0,927.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg27.setFill(linearGradient);
			   gundamLeftLeg27.setStroke(Color.BLACK);
			   gundamLeftLeg27.setStrokeWidth(2.0);
			   return gundamLeftLeg27;
			   
		   }
		   public Node gundamLeftLeg28() {
			   Polygon gundamLeftLeg28=new Polygon();
			   gundamLeftLeg28.getPoints().addAll(new Double[]{ 
				    	 918.0,902.0,
				    	 915.0,909.0,
				    	 912.0,914.0,
				    	 906.0,920.0,
				    	 901.0,924.0,
				    	 892.0,930.0,
				    	 885.0,935.0,
				    	 878.0,939.0,
				    	 870.0,943.0,
				    	 856.0,948.0,
				    	 856.0,991.0,
				    	 898.0,988.0,
				    	 928.0,939.0,
				    	 924.0,907.0,
				    	 922.0,904.0,
				    	 919.0,902.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   gundamLeftLeg28.setFill(linearGradient);
			   gundamLeftLeg28.setStroke(Color.BLACK);
			   gundamLeftLeg28.setStrokeWidth(2.0);
			   return gundamLeftLeg28;
			   
		   }
		   public Node gundamLeftLeg29() {
			   Polygon gundamLeftLeg29 = new Polygon();
			   gundamLeftLeg29.getPoints().addAll(new Double[]{ 
				    	 854.0,947.0,
				    	 849.0,949.0,
				    	 823.0,985.0,
				    	 856.0,991.0,
				    	 856.0,948.0,
				    	 855.0,948.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   gundamLeftLeg29.setFill(linearGradient);
			   gundamLeftLeg29.setStroke(Color.BLACK);
			   gundamLeftLeg29.setStrokeWidth(2.0);
			   return gundamLeftLeg29;
		   }
		   public Node gundamLeftLeg30() {
			   Polygon gundamLeftLeg30 = new Polygon();
			   gundamLeftLeg30.getPoints().addAll(new Double[]{ 
				    	 849.0,949.0,
				    	 813.0,1000.0,
				    	 780.0,960.0,
				    	 774.0,958.0,
				    	 800.0,941.0,
				    	 811.0,946.0,
				    	 818.0,948.0,
				    	 825.0,948.0,
				    	 834.0,948.0,
				    	 836.0,928.0,
				    	 839.0,933.0,
				    	 846.0,934.0,
				    	 845.0,948.0,
				    	 846.0,949.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   gundamLeftLeg30.setFill(linearGradient);
			   gundamLeftLeg30.setStroke(Color.BLACK);
			   gundamLeftLeg30.setStrokeWidth(2.0);
			   return gundamLeftLeg30;
		   }
		   public Node gundamLeftLeg31() {
			   Polygon gundamLeftLeg31 = new Polygon();
			   gundamLeftLeg31.getPoints().addAll(new Double[]{ 
				    	695.0,887.0,
				    	732.0,896.0,
				    	772.0,958.0,
				    	705.0,967.0,
				    	681.0,949.0,
				    	646.0,939.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg31.setFill(linearGradient);
			   gundamLeftLeg31.setStroke(Color.BLACK);
			   gundamLeftLeg31.setStrokeWidth(2.0);
			   return gundamLeftLeg31;
		   }
		   public Node gundamLeftLeg32() {
			   Polygon gundamLeftLeg32 = new Polygon();
			   gundamLeftLeg32.getPoints().addAll(new Double[]{ 
				    	646.0,939.0,
				    	640.0,937.0,
				    	639.0,937.0,
				    	588.0,990.0,
				    	588.0,993.0,
				    	591.0,999.0,
				    	647.0,1016.0,
				    	813.0,1000.0,
				    	780.0,960.0,
				    	774.0,958.0,
				    	772.0,958.0,
				    	705.0,967.0,
				    	681.0,949.0,
				    	
				    	
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg32.setFill(linearGradient);
			   gundamLeftLeg32.setStroke(Color.BLACK);
			   gundamLeftLeg32.setStrokeWidth(2.0);
			   return gundamLeftLeg32;
		   }
		   public Node gundamLeftLeg33() {
			   Polygon gundamLeftLeg33 = new Polygon();
			   gundamLeftLeg33.getPoints().addAll(new Double[]{ 
				    	588.0,990.0,
				    	588.0,993.0,
				    	591.0,999.0,
				    	645.0,1016.0,
				    	637.0,1006.0,
				    	636.0,1005.0,
				    	
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg33.setFill(linearGradient);
			   gundamLeftLeg33.setStroke(Color.BLACK);
			   gundamLeftLeg33.setStrokeWidth(2.0);
			   return gundamLeftLeg33;
			   
		   }
		   public Node gundamLeftLeg34() {
			   Polygon gundamLeftLeg34 = new Polygon();
			   gundamLeftLeg34.getPoints().addAll(new Double[]{ 
				    	916.0,959.0,
				    	902.0,981.0,
				    	921.0,978.0,
				    	921.0,977.0,
				    	
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamLeftLeg34.setFill(linearGradient);
			   gundamLeftLeg34.setStroke(Color.BLACK);
			   gundamLeftLeg34.setStrokeWidth(2.0);
			   return gundamLeftLeg34;  
		   }
		   public Node gundamRightLegOne() {
			   Polygon gundamRightLegOne = new Polygon();
			   gundamRightLegOne.getPoints().addAll(new Double[]{ 
				    	1066.0,705.0,
				    	1052.0,705.0,
				    	1038.0,709.0,
				    	1037.0,710.0,
				    	1036.0,713.0,
				    	1037.0,715.0,
				    	1034.0,724.0,
				    	1034.0,729.0,
				    	1046.0,771.0,
				    	1044.0,749.0,
				    	1072.0,743.0,
				    	1080.0,763.0,
				    	1080.0,767.0,
				    	1082.0,767.0,
				    	1087.0,747.0,
				    	1096.0,741.0,
				    	1091.0,735.0,
				    	1093.0,713.0,
				    	1089.0,709.0,
				    	1091.0,716.0,
				    	1091.0,721.0,
				    	1087.0,728.0,
				    	1070.0,728.0,
				    	
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLegOne.setFill(linearGradient);
			   gundamRightLegOne.setStroke(Color.BLACK);
			   gundamRightLegOne.setStrokeWidth(2.0);
			   return gundamRightLegOne;  
		   }
		   public Node gundamRightLegTwo() {
			   Polygon gundamRightLegTwo = new Polygon();
			   gundamRightLegTwo.getPoints().addAll(new Double[]{ 
					   	1046.0,771.0,
					   	1044.0,749.0,
				    	1072.0,743.0,
				    	
				    	1080.0,763.0,
				    	1080.0,767.0,
				    	1080.0,768.0,
				    	1075.0,770.0,
				    	1085.0,794.0,
				    	1085.0,795.0,
				    	1059.0,803.0,
				    	1055.0,803.0,
				    	1055.0,797.0,
				    	1048.0,790.0,
				    	
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLegTwo.setFill(linearGradient);
			   gundamRightLegTwo.setStroke(Color.BLACK);
			   gundamRightLegTwo.setStrokeWidth(2.0);
			   return gundamRightLegTwo;  
		   }
		   public Node gundamRightLegThree() {
			   Polygon gundamRightLegThree = new Polygon();
			   gundamRightLegThree.getPoints().addAll(new Double[]{ 
					   	1044.0,749.0,
					   	1046.0,771.0,
					   	1048.0,790.0,
					   	1055.0,797.0,
					   	1055.0,803.0,
					   	1059.0,803.0,
					   	1055.0,771.0,
					   	1062.0,774.0,
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLegThree.setFill(linearGradient);
			   gundamRightLegThree.setStroke(Color.BLACK);
			   gundamRightLegThree.setStrokeWidth(2.0);
			   return gundamRightLegThree;  
		   }
		   public Node gundamRightLegFour() {
			   Polygon gundamRightLegFour = new Polygon();
			   gundamRightLegFour.getPoints().addAll(new Double[]{ 
					   1044.0,749.0,
					   1062.0,774.0,
					   1081.0,768.0,
					   1072.0,743.0,
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLegFour.setFill(linearGradient);
			   gundamRightLegFour.setStroke(Color.BLACK);
			   gundamRightLegFour.setStrokeWidth(2.0);
			   return gundamRightLegFour;  
		   }
		   public Node gundamRightLegFive() {
			   Polygon gundamRightLegFive = new Polygon();
			   gundamRightLegFive.getPoints().addAll(new Double[]{ 
					   1055.0,803.0,
					   1059.0,803.0,
					   1085.0,795.0,
					   1107.0,835.0,
					   1107.0,837.0,
					   1103.0,837.0,
					   1094.0,822.0,
					   1093.0,822.0,
					   1076.0,828.0,
					   1079.0,835.0,
					   1079.0,836.0,
					   1073.0,841.0,
					   1057.0,823.0,
					   
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLegFive.setFill(linearGradient);
			   gundamRightLegFive.setStroke(Color.BLACK);
			   gundamRightLegFive.setStrokeWidth(2.0);
			   return gundamRightLegFive;  
		   }
		   public Node gundamRightLegSix() {
			   Polygon gundamRightLegSix = new Polygon();
			   gundamRightLegSix.getPoints().addAll(new Double[]{ 
					   1052.0,705.0,
					   1038.0,709.0,
					   1037.0,710.0,
					   1036.0,713.0,
					   1037.0,715.0,
					   1034.0,724.0,
					   1034.0,729.0,
					   1046.0,771.0,
					   1044.0,749.0,
					   1057.0,746.0,
					   1051.0,725.0,
					   1051.0,723.0,
					   1055.0,706.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLegSix.setFill(linearGradient);
			   gundamRightLegSix.setStroke(Color.BLACK);
			   gundamRightLegSix.setStrokeWidth(2.0);
			   return gundamRightLegSix;  
		   }
		   public Node gundamRightLegSeven() {
			   Polygon gundamRightLegSeven = new Polygon();
			   gundamRightLegSeven.getPoints().addAll(new Double[]{ 
					   1048.0,790.0,
					   1055.0,797.0,
					   1055.0,803.0,
					   1057.0,823.0,
					   1058.0,835.0,
					   1042.0,840.0,
					   1040.0,838.0,
					   1040.0,837.0,
					   1034.0,834.0,
					   1034.0,806.0,
					   1033.0,804.0,
					   1032.0,800.0,
					   1028.0,795.0,
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLegSeven.setFill(linearGradient);
			   gundamRightLegSeven.setStroke(Color.BLACK);
			   gundamRightLegSeven.setStrokeWidth(2.0);
			   return gundamRightLegSeven;  
		   }
		   public Node gundamRightLegEight() {
			   Polygon gundamRightLegEight = new Polygon();
			   gundamRightLegEight.getPoints().addAll(new Double[]{ 
					   1043.0,786.0,
					   1028.0,795.0,
					   1046.0,791.0,
					   1045.0,788.0,
					   
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLegEight.setFill(linearGradient);
			   gundamRightLegEight.setStroke(Color.BLACK);
			   gundamRightLegEight.setStrokeWidth(2.0);
			   return gundamRightLegEight;  
		   }
		   public Node gundamRightLegNine() {
			   Polygon gundamRightLegNine = new Polygon();
			   gundamRightLegNine.getPoints().addAll(new Double[]{ 
					   1055.0,797.0,
					   1057.0,823.0,
					   1058.0,835.0,
					   1042.0,840.0,
					   1040.0,838.0,
					   1036.0,802.0,
					   
																												      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLegNine.setFill(linearGradient);
			   gundamRightLegNine.setStroke(Color.BLACK);
			   gundamRightLegNine.setStrokeWidth(2.0);
			   return gundamRightLegNine;  
		   }
		   public Node gundamRightLegTen() {
			   Polygon gundamRightLegTen = new Polygon();
			   gundamRightLegTen.getPoints().addAll(new Double[]{ 
					   1036.0,802.0,
					   1049.0,799.0,
					   1051.0,829.0,
					   1040.0,830.0,
					   
																												      });
			   gundamRightLegTen.setFill(Color.BLACK);
			   return gundamRightLegTen;
		   }
		   public Node gundamRightLeg11() {
			   Polygon gundamRightLeg11 = new Polygon();
			   gundamRightLeg11.getPoints().addAll(new Double[]{ 
					  1055.0,803.0,
					  1059.0,803.0,
					  1076.0,828.0,
					  1079.0,835.0,
					  1079.0,836.0,
					  1073.0,841.0,
					  1057.0,823.0,
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg11.setFill(linearGradient);
			   gundamRightLeg11.setStroke(Color.BLACK);
			   gundamRightLeg11.setStrokeWidth(2.0);
			   return gundamRightLeg11;
		   }
		   public Node gundamRightLeg12() {
			   Polygon gundamRightLeg12 = new Polygon();
			   gundamRightLeg12.getPoints().addAll(new Double[]{ 
					 1043.0,786.0,
					 1045.0,788.0,
					 1046.0,791.0,
					 1048.0,791.0,
					 1048.0,784.0,
					 1046.0,784.0,
																												      });
			   gundamRightLeg12.setFill(Color.BLACK);
			   
			   return gundamRightLeg12;
		   }
		   public Node gundamRightLeg13() {
			   Polygon gundamRightLeg13 = new Polygon();
			   gundamRightLeg13.getPoints().addAll(new Double[]{ 
					1081.0,785.0,
					1082.0,785.0,
					1084.0,787.0,
					1085.0,787.0,
					1085.0,784.0,
					1087.0,784.0,
					1087.0,798.0,
					1100.0,810.0,
					1095.0,810.0,
					1094.0,811.0,
					1094.0,814.0,
					1085.0,797.0,
					1085.0,795.0,
																												      });
			   gundamRightLeg13.setFill(Color.BLACK);
			   
			   return gundamRightLeg13;
		   }
		   public Node gundamRightLeg14() {
			   Polygon gundamRightLeg14 = new Polygon();
			   gundamRightLeg14.getPoints().addAll(new Double[]{ 
					1099.0,810.0,
					1096.0,810.0,
					1095.0,812.0,
					1095.0,813.0,
					1099.0,818.0,
					1101.0,818.0,
					1103.0,816.0,
					1103.0,815.0,
																												      });
			   gundamRightLeg14.setFill(Color.RED);
			   
			   return gundamRightLeg14;
		   }
		   public Node gundamRightLeg15() {
			   Polygon gundamRightLeg15 = new Polygon();
			   gundamRightLeg15.getPoints().addAll(new Double[]{ 
					1103.0,837.0,
					1094.0,822.0,
					1076.0,828.0,
					1079.0,835.0,
					1079.0,836.0,
					1084.0,850.0,
					1084.0,852.0,
					1080.0,858.0,
					1080.0,860.0,
					1087.0,872.0,
					1089.0,872.0,
					1104.0,867.0,
					1111.0,850.0,
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg15.setFill(linearGradient);
			   gundamRightLeg15.setStroke(Color.BLACK);
			   gundamRightLeg15.setStrokeWidth(2.0);
			   return gundamRightLeg15;
		   }
		   public Node gundamRightLeg16() {
			   Polygon gundamRightLeg16 = new Polygon();
			   gundamRightLeg16.getPoints().addAll(new Double[]{ 
					1089.0,872.0,
					1087.0,872.0,
					1080.0,860.0,
					1080.0,858.0,
					1084.0,852.0,
					1084.0,850.0,
					1079.0,836.0,
					1079.0,835.0,
					1076.0,828.0,
					1091.0,855.0,
					1091.0,856.0,
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg16.setFill(linearGradient);
			   gundamRightLeg16.setStroke(Color.BLACK);
			   gundamRightLeg16.setStrokeWidth(2.0);
			   return gundamRightLeg16;
		   }
		   public Node gundamRightLeg17() {
			   Polygon gundamRightLeg17 = new Polygon();
			   gundamRightLeg17.getPoints().addAll(new Double[]{ 
					1111.0,819.0,
					1109.0,819.0,
					1108.0,820.0,
					1108.0,822.0,
					1113.0,840.0,
					1113.0,841.0,
					1109.0,846.0,
					1117.0,862.0,
					1119.0,862.0,
					1137.0,855.0,
					1139.0,842.0,
					1139.0,840.0,
					1130.0,828.0,
					1123.0,828.0,
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg17.setFill(linearGradient);
			   gundamRightLeg17.setStroke(Color.BLACK);
			   gundamRightLeg17.setStrokeWidth(2.0);
			   return gundamRightLeg17;
		   }
		   public Node gundamRightLeg18() {
			   Polygon gundamRightLeg18 = new Polygon();
			   gundamRightLeg18.getPoints().addAll(new Double[]{ 
					1108.0,822.0,
					1113.0,840.0,
					1113.0,841.0,
					1109.0,846.0,
					1117.0,862.0,
					1119.0,862.0,
					1120.0,841.0,
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg18.setFill(linearGradient);
			   gundamRightLeg18.setStroke(Color.BLACK);
			   gundamRightLeg18.setStrokeWidth(2.0);
			   return gundamRightLeg18;
		   }
		   public Node gundamRightleg19() {
			   Polygon gundamRightleg19 = new Polygon();
			   gundamRightleg19.getPoints().addAll(new Double[]{ 
					1105.0,831.0,
					1107.0,835.0,
					1107.0,837.0,
					1103.0,837.0,
					1109.0,845.0,
					1113.0,841.0,
					1113.0,840.0,
					1109.0,830.0,
					1106.0,830.0,
					1106.0,831.0,
																												      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightleg19.setFill(linearGradient);
			   gundamRightleg19.setStroke(Color.BLACK);
			   gundamRightleg19.setStrokeWidth(2.0);
			   return gundamRightleg19;
		   }
		   public Node gundamRightleg20() {
			   Polygon gundamRightleg20 = new Polygon();
			   gundamRightleg20.getPoints().addAll(new Double[]{ 
					1097.0,819.0,
					1101.0,819.0,
					1105.0,815.0,
					1111.0,815.0,
					1111.0,819.0,
					1108.0,819.0,
					1108.0,820.0,
					1108.0,822.0,
					1109.0,829.0,
					1109.0,830.0,
					1106.0,830.0,
					1106.0,831.0,
					1105.0,831.0,
					1104.0,831.0,
																												      });
			   gundamRightleg20.setFill(Color.BLACK);
			   
			   return gundamRightleg20;
		   }
		   public Node gundamRightleg21() {
			   Polygon gundamRightleg21 = new Polygon();
			   gundamRightleg21.getPoints().addAll(new Double[]{ 
					   1079.0,836.0,
					   1073.0,841.0,
					   1070.0,841.0,
					   1070.0,844.0,
					   1068.0,844.0,
					   1067.0,845.0,
					   1067.0,852.0,
					   1068.0,853.0,
					   1084.0,879.0,
					   1086.0,879.0,
					   1142.0,858.0,
					   1142.0,856.0,
					   1137.0,851.0,
					   1137.0,855.0,
					   1119.0,862.0,
					   1118.0,862.0,
					   1111.0,852.0,
					   1110.0,852.0,
					   1104.0,867.0,
					   1089.0,872.0,
					   1087.0,872.0,
					   1080.0,859.0,
					   1080.0,858.0,
					   1084.0,852.0,
					   1084.0,850.0,
																								      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightleg21.setFill(linearGradient);
			   gundamRightleg21.setStroke(Color.BLACK);
			   gundamRightleg21.setStrokeWidth(2.0);
			   return gundamRightleg21;
		   }
		   public Node gundamRightleg22() {
			   Polygon gundamRightleg22 = new Polygon();
			   gundamRightleg22.getPoints().addAll(new Double[]{ 
					   1067.0,845.0,
					   1068.0,844.0,
					   1070.0,844.0,
					   1071.0,844.0,
					   1074.0,847.0,
					   1075.0,852.0,
					   1075.0,855.0,
					   1074.0,856.0,
					   1070.0,856.0,
					   1067.0,852.0,
																								      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightleg22.setFill(linearGradient);
			   gundamRightleg22.setStroke(Color.BLACK);
			   gundamRightleg22.setStrokeWidth(2.0);
			   return gundamRightleg22;
		   }
		   public Node gundamRightleg23() {
			   Polygon gundamRightleg23 = new Polygon();
			   gundamRightleg23.getPoints().addAll(new Double[]{ 
					   1028.0,794.0,
					   1032.0,800.0,
					   1033.0,804.0,
					   1034.0,806.0,
					   1034.0,834.0,
					   1034.0,849.0,
					   1023.0,865.0,
					   990.0,870.0,
					   989.0,869.0,
					   984.0,818.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightleg23.setFill(linearGradient);
			   gundamRightleg23.setStroke(Color.BLACK);
			   gundamRightleg23.setStrokeWidth(2.0);
			   return gundamRightleg23;
		   }
		   public Node gundamRightleg24() {
			   Polygon gundamRightleg24 = new Polygon();
			   gundamRightleg24.getPoints().addAll(new Double[]{ 
					   1016.0,801.0,
					   1020.0,806.0,
					   1021.0,812.0,
					   1020.0,849.0,
					   1018.0,853.0,
					   1017.0,856.0,
					   1015.0,861.0,
					   1009.0,867.0,
					   989.0,869.0,
					   984.0,818.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightleg24.setFill(linearGradient);
			   gundamRightleg24.setStroke(Color.BLACK);
			   gundamRightleg24.setStrokeWidth(2.0);
			   return gundamRightleg24;
		   }
		   public Node gundamRightleg25() {
			   Polygon gundamRightleg25 = new Polygon();
			   gundamRightleg25.getPoints().addAll(new Double[]{ 
					   1033.0,847.0,
					   1024.0,847.0,
					   1019.0,856.0,
					   1019.0,858.0,
					   1020.0,859.0,
					   1028.0,858.0,
					   1033.0,849.0,
																								      });
			   gundamRightleg25.setFill(Color.BLACK);
			  
			   return gundamRightleg25;
		   }
		   public Node gundamRightleg26() {
			   Polygon gundamRightleg26 = new Polygon();
			   gundamRightleg26.getPoints().addAll(new Double[]{ 
					   1068.0,854.0,
					   1066.0,854.0,
					   1065.0,855.0,
					   1064.0,855.0,
					   1063.0,855.0,
					   1062.0,856.0,
					   1062.0,860.0,
					   1071.0,878.0,
					   1071.0,879.0,
					   1069.0,891.0,
					   1067.0,898.0,
					   1066.0,903.0,
					   1063.0,912.0,
					   1059.0,920.0,
					   1056.0,925.0,
					   1055.0,927.0,
					   1052.0,931.0,
					   1052.0,932.0,
					   1057.0,938.0,
					   1068.0,943.0,
					   1069.0,943.0,
					   1092.0,891.0,
					   1092.0,890.0,
					   
																								      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightleg26.setFill(linearGradient);
			   gundamRightleg26.setStroke(Color.BLACK);
			   gundamRightleg26.setStrokeWidth(2.0);
			   return gundamRightleg26;
		   }
		   public Node gundamRightleg27() {
			   Polygon gundamRightleg27 = new Polygon();
			   gundamRightleg27.getPoints().addAll(new Double[]{ 
					   1034.0,834.0,
					   1040.0,838.0,
					   1042.0,840.0,
					   1052.0,837.0,
					   1071.0,878.0,
					   1071.0,879.0,
					   1069.0,891.0,
					   1067.0,898.0,
					   1066.0,903.0,
					   1063.0,912.0,
					   1059.0,920.0,
					   1056.0,925.0,
					   1055.0,927.0,
					   1052.0,931.0,
					   1046.0,942.0,
					   1041.0,949.0,
					   1034.0,956.0,
					   1029.0,960.0,
					   1028.0,960.0,
					   1019.0,952.0,
					   1013.0,867.0,
					   1023.0,865.0,
					   1029.0,858.0,
					   1034.0,850.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightleg27.setFill(linearGradient);
			   gundamRightleg27.setStroke(Color.BLACK);
			   gundamRightleg27.setStrokeWidth(2.0);
			   return gundamRightleg27;
		   }
		   public Node gundamRightLeg28() {
			   Polygon gundamRightLeg28 = new Polygon();
			   gundamRightLeg28.getPoints().addAll(new Double[]{ 
					   1092.0,891.0,
					   1069.0,943.0,
					   1068.0,943.0,
					   1057.0,938.0,
					   1075.0,892.0,
																								      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg28.setFill(linearGradient);
			   gundamRightLeg28.setStroke(Color.BLACK);
			   gundamRightLeg28.setStrokeWidth(2.0);
			   return gundamRightLeg28;
		   }
		   public Node gundamRightLeg29() {
			   Polygon gundamRightLeg29 = new Polygon();
			   gundamRightLeg29.getPoints().addAll(new Double[]{ 
					   1075.0,892.0,
					   1083.0,892.0,
					   1066.0,933.0,
					   1065.0,933.0,
					   1060.0,930.0,
																								      });
			   gundamRightLeg29.setFill(Color.BLACK);
			   
			   return gundamRightLeg29;
		   }
		   public Node gundamRightLeg30() {
			   Polygon gundamRightLeg30 = new Polygon();
			   gundamRightLeg30.getPoints().addAll(new Double[]{ 
					   1034.0,834.0,
					   1036.0,836.0,
					   1050.0,882.0,
					   1050.0,883.0,
					   1049.0,893.0,
					   1047.0,904.0,
					   1043.0,915.0,
					   1040.0,922.0,
					   1035.0,933.0,
					   1030.0,941.0,
					   1026.0,947.0,
					   1019.0,952.0,
					   1013.0,867.0,
					   1023.0,865.0,
					   1029.0,858.0,
					   1034.0,850.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg30.setFill(linearGradient);
			   gundamRightLeg30.setStroke(Color.BLACK);
			   gundamRightLeg30.setStrokeWidth(2.0);
			   return gundamRightLeg30; 
		   }
		   public Node gundamRightLeg31() {
			   Polygon gundamRightLeg31 = new Polygon();
			   gundamRightLeg31.getPoints().addAll(new Double[]{ 
					   1013.0,867.0,
					   1019.0,952.0,
					   1016.0,952.0,
					   1011.0,948.0,
					   1008.0,868.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg31.setFill(linearGradient);
			   gundamRightLeg31.setStroke(Color.BLACK);
			   gundamRightLeg31.setStrokeWidth(2.0);
			   return gundamRightLeg31; 
		   }
		   public Node gundamRightLeg32() {
			   Polygon gundamRightLeg32 = new Polygon();
			   gundamRightLeg32.getPoints().addAll(new Double[]{ 
					  1013.0,867.0,
					  1017.0,931.0,
					  1015.0,931.0,
					  1010.0,926.0,
					  1008.0,868.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   
			   gundamRightLeg32.setFill(linearGradient);
			   gundamRightLeg32.setStroke(Color.BLACK);
			   gundamRightLeg32.setStrokeWidth(2.0);
			   return gundamRightLeg32; 
		   }
		   public Node gundamRightLeg33() {
			   Polygon gundamRightLeg33 = new Polygon();
			   gundamRightLeg33.getPoints().addAll(new Double[]{ 
					  1008.0,868.0,
					  1011.0,948.0,
					  1006.0,944.0,
					  1002.0,940.0,
					  999.0,935.0,
					  997.0,931.0,
					  995.0,924.0,
					  997.0,892.0,
					  998.0,869.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg33.setFill(linearGradient);
			   gundamRightLeg33.setStroke(Color.BLACK);
			   gundamRightLeg33.setStrokeWidth(2.0);
			   return gundamRightLeg33; 
		   }
		   
		   public Node gundamRightLeg34() {
			   Polygon gundamRightLeg34 = new Polygon();
			   gundamRightLeg34.getPoints().addAll(new Double[]{ 
					  1058.0,825.0,
					  1072.0,840.0,
					  1072.0,841.0,
					  1071.0,841.0,
					  1070.0,842.0,
					  1070.0,844.0,
					  1068.0,844.0,
					  1067.0,845.0,
					  1067.0,851.0,
					  1067.0,853.0,
					  1066.0,853.0,
					  1065.0,854.0,
					  1063.0,854.0,
					  1062.0,855.0,
					  1062.0,858.0,
					  1061.0,858.0,
					  1052.0,837.0,
					  1058.0,835.0,
																								      });
			   gundamRightLeg34.setFill(Color.BLACK);
			   return gundamRightLeg34; 
		   }
		   public Node gundamRightLeg35() {
			   Polygon gundamRightLeg35 = new Polygon();
			   gundamRightLeg35.getPoints().addAll(new Double[]{ 
					  1068.0,854.0,
					  1066.0,854.0,
					  1065.0,855.0,
					  1063.0,855.0,
					  1063.0,860.0,
					  1070.0,877.0,
					  1080.0,873.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg35.setFill(linearGradient);
			   gundamRightLeg35.setStroke(Color.BLACK);
			   gundamRightLeg35.setStrokeWidth(2.0);
			   return gundamRightLeg35; 
		   }
		   public Node gundamRightLeg36() {
			   Polygon gundamRightLeg36 = new Polygon();
			   gundamRightLeg36.getPoints().addAll(new Double[]{ 
					  1137.0,851.0,
					  1141.0,855.0,
					  1143.0,855.0,
					  1143.0,853.0,
					  1138.0,846.0,
																								      });
			   gundamRightLeg36.setFill(Color.BLACK);
			   return gundamRightLeg36; 
		   }
		   public Node gundamRightLeg37() {
			   Polygon gundamRightLeg37 = new Polygon();
			   gundamRightLeg37.getPoints().addAll(new Double[]{ 
					  1138.0,846.0,
					  1142.0,851.0,
					  1148.0,851.0,
					  1148.0,848.0,
					  1142.0,840.0,
					  1138.0,835.0,
					  1136.0,836.0,
					  1139.0,840.0,
					  1139.0,843.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg37.setFill(linearGradient);
			   gundamRightLeg37.setStroke(Color.BLACK);
			   gundamRightLeg37.setStrokeWidth(2.0);
			   return gundamRightLeg37; 
		   }
		   public Node gundamRightLeg38() {
			   Polygon gundamRightLeg38 = new Polygon();
			   gundamRightLeg38.getPoints().addAll(new Double[]{ 
					  1143.0,851.0,
					  1143.0,855.0,
					  1150.0,865.0,
					  1152.0,865.0,
					  1157.0,862.0,
					  1157.0,860.0,
					  1149.0,851.0,
																								      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg38.setFill(linearGradient);
			   gundamRightLeg38.setStroke(Color.BLACK);
			   gundamRightLeg38.setStrokeWidth(2.0);
			   return gundamRightLeg38; 
		   }
		   public Node gundamRightLeg39() {
			   Polygon gundamRightLeg39 = new Polygon();
			   gundamRightLeg39.getPoints().addAll(new Double[]{ 
					  1157.0,862.0,
					  1150.0,851.0,
					  1138.0,835.0,
					  1135.0,835.0,
					  1131.0,829.0,
					  1133.0,829.0,
					  1138.0,832.0,
					  1146.0,832.0,
					  1146.0,837.0,
					  1159.0,851.0,
					  1162.0,862.0,
																								      });
			   gundamRightLeg39.setFill(Color.BLACK);
			   return gundamRightLeg39; 
		   }
		   public Node gundamRightLeg40() {
			   Polygon gundamRightLeg40 = new Polygon();
			   gundamRightLeg40.getPoints().addAll(new Double[]{ 
					  1157.0,863.0,
					  1157.0,868.0,
					  1166.0,892.0,
					  1174.0,903.0,
					 // 1174.0,896.0,
					  1172.0,896.0,
					  1161.0,863.0,
					  
																								      });
			   Stop[] stops = new Stop[] { 
					   new Stop(1, Color.rgb(164, 131, 33)),  
					   new Stop(0, Color.rgb(237, 220, 114))
			   						};  
			   LinearGradient linearGradient = 
					   new LinearGradient(0, 0, 0, 1, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg40.setFill(linearGradient);
			   gundamRightLeg40.setStroke(Color.BLACK);
			   gundamRightLeg40.setStrokeWidth(2.0);
			   return gundamRightLeg40; 
		   }
		   public Node gundamRightLeg41() {
			   Polygon gundamRightLeg41 = new Polygon();
			   gundamRightLeg41.getPoints().addAll(new Double[]{ 
					  1157.0,863.0,
					  1155.0,863.0,
					  1153.0,864.0,
					  1152.0,865.0,
					  1151.0,865.0,
					  1150.0,866.0,
					  1149.0,866.0,
					  1166.0,892.0,
					  
																								      });
			   gundamRightLeg41.setFill(Color.BLACK);
			   return gundamRightLeg41; 
		   }
		   public Node gundamRightLeg42() {
			   Polygon gundamRightLeg42 = new Polygon();
			   gundamRightLeg42.getPoints().addAll(new Double[]{ 
					  1147.0,836.0,
					  1151.0,838.0,
					  1163.0,838.0,
					  1163.0,839.0,
					  1172.0,847.0,
					  1175.0,859.0,
					  1176.0,886.0,
					  1175.0,895.0,
					  1173.0,897.0,
					  1161.0,863.0,
					  1160.0,855.0,
					  1159.0,850.0,
					  1147.0,838.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg42.setFill(linearGradient);
			   gundamRightLeg42.setStroke(Color.BLACK);
			   gundamRightLeg42.setStrokeWidth(2.0);
			   return gundamRightLeg42; 
		   }
		   public Node gundamRightLeg43() {
			   Polygon gundamRightLeg43 = new Polygon();
			   gundamRightLeg43.getPoints().addAll(new Double[]{ 
					  1136.0,860.0,
					  1140.0,865.0,
					  1148.0,885.0,
					  1148.0,886.0,
					  1148.0,887.0,
					  1114.0,887.0,
					  1099.0,874.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg43.setFill(linearGradient);
			   gundamRightLeg43.setStroke(Color.BLACK);
			   gundamRightLeg43.setStrokeWidth(2.0);
			   return gundamRightLeg43; 
		   }
		   public Node gundamRightLeg44() {
			   Polygon gundamRightLeg44 = new Polygon();
			   gundamRightLeg44.getPoints().addAll(new Double[]{ 
					  1143.0,853.0,
					  1143.0,857.0,
					  1136.0,860.0,
					  1140.0,865.0,
					  1148.0,885.0,
					  1148.0,886.0,
					  1148.0,887.0,
					  1114.0,887.0,
					  1099.0,874.0,
					  1084.0,879.0,
					  1092.0,889.0,
					  1092.0,891.0,
					  1069.0,943.0,
					  1066.0,943.0,
					  1066.0,944.0,
					  1076.0,969.0,
					  1101.0,899.0,
					  1102.0,898.0,
					  1165.0,897.0,
					  1192.0,937.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   
			   gundamRightLeg44.setFill(linearGradient);
			   gundamRightLeg44.setStroke(Color.BLACK);
			   gundamRightLeg44.setStrokeWidth(2.0);
			   return gundamRightLeg44; 
		   }
		   public Node gundamRightLeg45() {
			   Polygon gundamRightLeg45 = new Polygon();
			   gundamRightLeg45.getPoints().addAll(new Double[]{ 
					  1076.0,969.0,
					  1101.0,899.0,
					  1102.0,898.0,
					  1165.0,897.0,
					  1212.0,969.0,
					  1142.0,970.0,
					  1127.0,996.0,
					  1126.0,996.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(1, Color.rgb(82, 125, 234)),  
				         new Stop(0, Color.rgb(42, 76, 162))
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(0, 1, 0, 0, true, CycleMethod.NO_CYCLE, stops);
			   gundamRightLeg45.setFill(linearGradient);
			   gundamRightLeg45.setStroke(Color.BLACK);
			   gundamRightLeg45.setStrokeWidth(2.0);
			   return gundamRightLeg45; 
		   }
		   public Node gundamRightLeg46() {
			   Polygon gundamRightLeg46 = new Polygon();
			   gundamRightLeg46.getPoints().addAll(new Double[]{ 
					  1076.0,969.0,
					  1126.0,996.0,
					  1127.0,996.0,
					  1142.0,970.0,
					  1212.0,969.0,
					  1232.0,995.0,
					  1254.0,1046.0,
					  1254.0,1047.0,
					  1169.0,1052.0,
					  1058.0,1002.0,
					  1068.0,969.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   gundamRightLeg46.setFill(linearGradient);
			   gundamRightLeg46.setStroke(Color.BLACK);
			   gundamRightLeg46.setStrokeWidth(2.0);
			   return gundamRightLeg46; 
		   }
		   public Node gundamRightLeg47() {
			   Polygon gundamRightLeg47 = new Polygon();
			   gundamRightLeg47.getPoints().addAll(new Double[]{ 
					  1076.0,969.0,
					  1068.0,969.0,
					  1058.0,1002.0,
					  1042.0,948.0,
					  1046.0,943.0,
					  1048.0,939.0,
					  1051.0,935.0,
					  1051.0,933.0,
					  1053.0,934.0,
					  1057.0,938.0,
					  1066.0,943.0,
					  1066.0,944.0,
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   gundamRightLeg47.setFill(linearGradient);
			   gundamRightLeg47.setStroke(Color.BLACK);
			   gundamRightLeg47.setStrokeWidth(2.0);
			   return gundamRightLeg47; 
		   }
		   public Node gundamRightLeg48() {
			   Polygon gundamRightLeg48 = new Polygon();
			   gundamRightLeg48.getPoints().addAll(new Double[]{ 
					  1042.0,948.0,
					  1047.0,965.0,
					  1047.0,989.0,
					  1045.0,989.0,
					  1026.0,979.0,
					  1015.0,952.0,
					  1020.0,952.0,
					  1027.0,960.0,
					  1029.0,960.0,
					  
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   gundamRightLeg48.setFill(linearGradient);
			   gundamRightLeg48.setStroke(Color.BLACK);
			   gundamRightLeg48.setStrokeWidth(2.0);
			   
			   Polygon gundamRightLeg49 = new Polygon();
			   gundamRightLeg49.getPoints().addAll(new Double[]{ 
					  1047.0,965.0,
					  1047.0,989.0,
					  1054.0,989.0,
					  
																								      });
			   Stop[] stopsTwo = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradientTwo = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stopsTwo); 
			   
			   gundamRightLeg49.setFill(linearGradientTwo);
			   gundamRightLeg49.setStroke(Color.BLACK);
			   gundamRightLeg49.setStrokeWidth(2.0);
			   Group g= new Group();
			   return g; 
		   }
		  // public Node gundamRightLeg49() {
			  
			   
		  // }
		   public Node gundamRightLeg50() {
			   Polygon gundamRightLeg50 = new Polygon();
			   gundamRightLeg50.getPoints().addAll(new Double[]{ 
					  1254.0,1047.0,
					  1254.0,1046.0,
					  1251.0,1039.0,
					  1179.0,1042.0,
					  1170.0,1052.0,
					  
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   gundamRightLeg50.setFill(linearGradient);
			   gundamRightLeg50.setStroke(Color.BLACK);
			   gundamRightLeg50.setStrokeWidth(2.0);
			   return gundamRightLeg50; 
		   }
		   public Node chinLeftOne() {
			   Polygon chinLeftOne = new Polygon();
			   chinLeftOne.getPoints().addAll(new Double[]{ 
					 871.0,578.0,
					 871.0,575.0,
					 866.0,564.0,
					 861.0,558.0,
					 858.0,558.0,
					 855.0,578.0,
					  
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   chinLeftOne.setFill(linearGradient);
			   chinLeftOne.setStroke(Color.BLACK);
			   chinLeftOne.setStrokeWidth(2.0);
			   return chinLeftOne; 
		   }
		   public Node chinLeftTwo() {
			   Polygon chinLeftTwo = new Polygon();
			   chinLeftTwo.getPoints().addAll(new Double[]{ 
					 858.0,558.0,
					 855.0,578.0,
					 846.0,578.0,
					 851.0,558.0,
					  
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   chinLeftTwo.setFill(linearGradient);
			   chinLeftTwo.setStroke(Color.BLACK);
			   chinLeftTwo.setStrokeWidth(2.0);
			   return chinLeftTwo; 
		   }
		   public Node smallRedOne() {
			   Polygon smallRedOne = new Polygon();
			   smallRedOne.getPoints().addAll(new Double[]{ 
					 848.0,558.0,
					 847.0,558.0,
					 845.0,560.0,
					 845.0,563.0,
					 847.0,563.0,
					 848.0,562.0,
					  
																								      });
			   smallRedOne.setFill(Color.RED);
			   
			   return smallRedOne; 
		   }
		   public Node smallRedTwo() {
			   Polygon smallRedTwo = new Polygon();
			   smallRedTwo.getPoints().addAll(new Double[]{ 
					 835.0,576.0,
					 833.0,576.0,
					 831.0,578.0,
					 831.0,580.0,
					 833.0,580.0,
					 835.0,578.0,
					  
																								      });
			   smallRedTwo.setFill(Color.RED);
			   
			   return smallRedTwo; 
		   }
		   public Node smallRedThree() {
			   Polygon smallRedThree = new Polygon();
			   smallRedThree.getPoints().addAll(new Double[]{ 
					 838.0,583.0,
					 838.0,582.0,
					 837.0,581.0,
					 827.0,581.0,
					 826.0,585.0,
					 833.0,586.0,
					  
																								      });
			   Stop[] stops = new Stop[] { 
				         new Stop(0, Color.rgb(255, 71, 26)),  
				         new Stop(1, Color.DARKRED),
				         
				      };  
				      LinearGradient linearGradient = 
				         new LinearGradient(1, 0 ,0, 0, true, CycleMethod.NO_CYCLE, stops); 
			   smallRedThree.setFill(linearGradient);
			   return smallRedThree;
			   
		   }
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////gundam group method Transition and SequentialTransition////////////////////////////////////////////////////////////////////////////////////////////////////////////////
		   public Node Animation() {
			   
			   Group g = new Group();
			   g.getChildren().add(leftBigAngleOne());
			      g.getChildren().add(leftSecondAngleTwo());
			      g.getChildren().add(leftSecondAngleThree());
			      g.getChildren().add(headAngleUpOne()); 
			      g.getChildren().add(headAngleUpTwo());
			      g.getChildren().add(headSkinHideUpOne());
			      g.getChildren().add(headSkinHideDownTwo());
			      g.getChildren().add( headEyeOne());
			      g.getChildren().add(headBrowSkinone());
			      g.getChildren().add(headBrowSkinTwo());
			      g.getChildren().add(headBrowSkinThree());
			      g.getChildren().add(headBrowSkinFour());
			      g.getChildren().add( headBrowSkinFive());
			      g.getChildren().add(headBrowSkinSix());
			      g.getChildren().add(rightBigAngleOne());
			      g.getChildren().add(rightBigAngleTwo());
			      g.getChildren().add(rightSecondAngleOne());
			      g.getChildren().add(rightSecondAngleTwo());
			      g.getChildren().add(rightSecondAngleThree());
			      g.getChildren().add(smallSizeHead());
			      g.getChildren().add(sideHeadOne());
			      g.getChildren().add(sideHeadLine());
			      g.getChildren().add(behindHeadLine());
			      g.getChildren().add(faceHeadHelmetOne());
			      g.getChildren().add(faceHeadHelmetTwo());
			      g.getChildren().add(eyelashDown());
			      g.getChildren().add(eyeLashDownTwo());
			      g.getChildren().add(nose());
			      g.getChildren().add(eyeLashDownThree());
			      g.getChildren().add(blackSkinFace());
			      g.getChildren().add(eyeBallOne());
			      g.getChildren().add(eyeBallTwo());
			      g.getChildren().add(helmetSkinRight());
			      g.getChildren().add(monthOne());
			      g.getChildren().add(monthTwo());
			      g.getChildren().add(faceHeadHelmetThree());
			      g.getChildren().add(chinOne());
			      g.getChildren().add(chinTwo());
			      g.getChildren().add(chinThree());
			      g.getChildren().add(mouthThree());
			      g.getChildren().add(mouthFour());
			      g.getChildren().add(faceHeadHelmetFour());
			      g.getChildren().add(faceHeadHelmetFive());
			      g.getChildren().add(leftVentOne());
			      g.getChildren().add(leftVentTwo());
			      g.getChildren().add(leftVentThree());
			      g.getChildren().add(leftVentFour());
			      g.getChildren().add(headEyeTwo());
			      g.getChildren().add(headEyeThree());
			      g.getChildren().add(rightVentOne());
			      g.getChildren().add(rightVentTwo());
			      g.getChildren().add(rightVentThree());
			      g.getChildren().add(rightVentFour());
			      g.getChildren().add(ShadowBlack());
			      g.getChildren().add(gundampantsOne());
			      g.getChildren().add(gundampantsTwo());
			      g.getChildren().add(gundampantsThree());
			      g.getChildren().add(gundampantsFour());
			      g.getChildren().add(gundampantsFive());
			      g.getChildren().add(gundampantsSix());
			      g.getChildren().add(gundampantsSeven());
			      g.getChildren().add(gundampantsEight());
			      g.getChildren().add(gundampantsNine());
			      g.getChildren().add(gundampantsTen());
			      g.getChildren().add(gundampants11());
			      g.getChildren().add(gundampants12());
			      g.getChildren().add(gundampants13());
			      g.getChildren().add(gundampants14());
			      g.getChildren().add(gundampants15());
			      g.getChildren().add(gundampants16());
			      g.getChildren().add(gundampants17());
			      g.getChildren().add(gundampants18());
			      g.getChildren().add(gundampants19());
			      g.getChildren().add(gundampants20());
			      g.getChildren().add(gundampants21());
			      g.getChildren().add(gundampants22());
			      g.getChildren().add(gundampants23());
			      g.getChildren().add(gundampants24());
			      g.getChildren().add(gundampants25());
			      g.getChildren().add(gundampants26());
			      g.getChildren().add(gundamLeftLegOne());
			      g.getChildren().add(gundampants27());
			      g.getChildren().add(gundamLeftLegTwo());
			      g.getChildren().add(gundamLeftLegThree());
			      g.getChildren().add(gundamLeftLegFour());
			      g.getChildren().add(gundamLeftLegFive());
			      g.getChildren().add(gundamLeftLegSix());
			      g.getChildren().add(gundamLeftLegSeven());
			      g.getChildren().add(gundamLeftLegeight());
			      g.getChildren().add(gundamLeftLegnine());
			      g.getChildren().add(gundamLeftLegTen());
			      g.getChildren().add(gundamLeftLeg11());
			      g.getChildren().add(gundamLeftLeg12());
			      g.getChildren().add(gundamLeftLeg13());
			      g.getChildren().add(gundamLeftLeg14());
			      g.getChildren().add(gundamLeftLeg15());
			      g.getChildren().add(gundamLeftLeg16());
			      g.getChildren().add(gundamLeftLeg17());
			      g.getChildren().add(gundamLeftLeg18());
			      g.getChildren().add(gundamLeftLeg19());
			      g.getChildren().add(gundamLeftLeg20());
			      g.getChildren().add(gundamLeftLeg21());
			      g.getChildren().add(gundamLeftLeg22());
			      g.getChildren().add(gundamLeftLeg23());
			      g.getChildren().add(gundamLeftLeg24());
			      g.getChildren().add(gundamLeftLeg25());
			      g.getChildren().add(gundamLeftLet26());
			      g.getChildren().add(gundamLeftLeg27());
			      g.getChildren().add(gundamLeftLeg28());
			      g.getChildren().add(gundamLeftLeg29());
			      g.getChildren().add(gundamLeftLeg30());
			      g.getChildren().add(gundamLeftLeg31());
			      g.getChildren().add(gundamLeftLeg32());
			      g.getChildren().add(gundamLeftLeg33());
			      g.getChildren().add(gundamLeftLeg34());
			      g.getChildren().add(gundamRightLegOne());
			      g.getChildren().add(gundamRightLegTwo());
			      g.getChildren().add(gundamRightLegThree());
			      g.getChildren().add(gundamRightLegFour());
			      g.getChildren().add(gundamRightLegFive());
			      g.getChildren().add(gundamRightLegSix());
			      g.getChildren().add(gundamRightLegSeven());
			      g.getChildren().add(gundamRightLegEight());
			      g.getChildren().add(gundamRightLegNine());
			      g.getChildren().add(gundamRightLegTen());
			      g.getChildren().add(gundamRightLeg11());
			      g.getChildren().add(gundamRightLeg12());
			      g.getChildren().add(gundamRightLeg13());
			      g.getChildren().add(gundamRightLeg14());
			      g.getChildren().add(gundamRightLeg15());
			      g.getChildren().add(gundamRightLeg16());
			      g.getChildren().add(gundamRightLeg17());
			      g.getChildren().add(gundamRightLeg18());
			      g.getChildren().add(gundamRightleg19());
			      g.getChildren().add(gundamRightleg20());
			      g.getChildren().add(gundamRightleg21());
			      g.getChildren().add(gundamRightleg22());
			      g.getChildren().add(gundamRightleg23());
			      g.getChildren().add(gundamRightleg24());
			      g.getChildren().add(gundamRightleg25());
			      g.getChildren().add(gundamRightleg26());
			      g.getChildren().add(gundamRightleg27());
			      g.getChildren().add(gundamRightLeg28());
			      g.getChildren().add(gundamRightLeg29());
			      g.getChildren().add(gundamRightLeg30());
			      g.getChildren().add(gundamRightLeg31());
			      g.getChildren().add(gundamRightLeg32());
			      g.getChildren().add(gundamRightLeg33());
			      g.getChildren().add(gundamRightLeg34());
			      g.getChildren().add(gundamRightLeg35());
			      g.getChildren().add(gundamRightLeg36());
			      g.getChildren().add(gundamRightLeg37());
			      g.getChildren().add(gundamRightLeg38());
			      g.getChildren().add(gundamRightLeg39());
			      g.getChildren().add(gundamRightLeg40());
			      g.getChildren().add(gundamRightLeg41());
			      g.getChildren().add(gundamRightLeg42());
			      g.getChildren().add(gundamRightLeg43());
			      g.getChildren().add(gundamRightLeg44());
			      g.getChildren().add(gundamRightLeg45());
			      g.getChildren().add(gundamRightLeg46());
			      g.getChildren().add(gundamRightLeg47());
			      g.getChildren().add(gundamRightLeg48());
			      g.getChildren().add(gundamRightLeg50());
			      g.getChildren().add(chinLeftOne());
			      g.getChildren().add(chinLeftTwo());
			      g.getChildren().add(smallRedOne());
			      g.getChildren().add(smallRedTwo());
			      g.getChildren().add(smallRedThree());
			      /////////////new test rotate////////
			      g.getChildren().add(rotate());
			      ///test//
			      g.getChildren().add(rightShoulderOne());
			      //test//
			      g.getChildren().add(rotateTwo());
			     
			      
			      
			      
			      //test three//
			      g.getChildren().add(Body());
			      //test two//
			      g.getChildren().add(bodyLion());
			   //Creating Translate Transition 
			      TranslateTransition translateTransition = new TranslateTransition(); 
			      
			      //Setting the duration of the transition  
			      translateTransition.setDuration(Duration.millis(1000)); 
			      
			      //Setting the node for the transition 
			      translateTransition.setNode(g); 
			      
			      //Setting the value of the transition along the x axis. 
			      translateTransition.setByY(80);

			      //Setting the cycle count for the transition 
			      translateTransition.setCycleCount(5000000); 
			      
			      //Setting auto reverse value to false 
			      translateTransition.setAutoReverse(true); 
			      
			      //Playing the animation 
			      translateTransition.play();
			      
			      BoxBlur bb = new BoxBlur();
			        bb.setWidth(2);
			        bb.setHeight(2);
			        bb.setIterations(2);
			        g.setEffect(bb);
			        
			        ///////////////////////////////////test/////////////////////////////////////
			        //Setting durations for the transitions  
			         Duration dur1 = Duration.millis(1000);  
			         Duration dur2 = Duration.millis(500);  
			       
			           
			         //Setting the pause transition  
			         PauseTransition pause = new PauseTransition(Duration.millis(1000));  
			           
			         //Setting the fade transition   
			         FadeTransition fade = new FadeTransition(dur2);  
			         fade.setFromValue(1.0f);  
			         fade.setToValue(0.3f);  
			         fade.setCycleCount(2);  
			         fade.setAutoReverse(true);  
			           
			         //Setting Translate transition  
			         TranslateTransition translate = new TranslateTransition(dur1);  
			         translate.setToX(-550f);
			         translate.setCycleCount(2);  
			         translate.setAutoReverse(true); 
			         
			         //Setting Translate transition  
			         TranslateTransition translateTwo = new TranslateTransition(dur1);  
			         translateTwo.setToX(550f);
			         translateTwo.setCycleCount(2);  
			         translateTwo.setAutoReverse(true); 
			         
			           
			         //Setting Rotate Transition   
			        // RotateTransition rotate = new RotateTransition(dur2);  
			        // rotate.setByAngle(180f);  
			        // rotate.setCycleCount(4);  
			        // rotate.setAutoReverse(true);  
			           
			         //Setting Scale Transition   
			         ScaleTransition scale = new ScaleTransition(dur1);  
			         scale.setByX(1.5f);  
			         scale.setByY(1.2f);  
			         scale.setCycleCount(2);  
			         scale.setAutoReverse(true);  
			           
			         //Instantiating Sequential Transition class by passing the list of transitions into its constructor  
			         SequentialTransition seqT = new SequentialTransition (g, pause, fade, translate,translateTwo,  scale);  
			           
			         //playing the transition   
			         seqT.play();  
			        ////////////////////////////////////////////////////////////////////////////
			      
			      return g;
		   }
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
///////////////////////////////method stage for call Node method oop/////////////////////////////////////
		   @Override
		   public void start(Stage stage) throws Exception{ 
		      //Creating a Polygon  
			  gundamTryon gundam = new gundamTryon();
			Group root = new Group();
			root.getChildren().add(gundam.image());
			root.getChildren().add(gundam.logo());
			Scene scene = new Scene( root, 1920, 1080);

	        // circle container
	        Pane container = new Pane();

	        // circle container is a child of the root pane
	        root.getChildren().add(container);

	        
	        int spawnNodes = 800;

	        // spawn the nodes (circles)
	        for (int i = 0; i < spawnNodes; i++) {
	            spawnNode(scene, container);
	        }
	        
	        //animation//
		      root.getChildren().add(gundam.Animation());

		       

		      //Setting title to the Stage 
		      stage.setTitle("Drawing a Gundam"); 
		         
		      //Adding scene to the stage 
		      stage.setScene(scene);
		      
		      
		      
		      //Displaying the contents of the stage 
		      stage.show(); 
		   }
////////////////////////////////////////////////////////////////////////////////////////////////////////		   
/////////////////////////////////////////////////////////////////////circle effect function/////////////////////////////////////////////////////////////
		   private void spawnNode(Scene scene, Pane container) {

		        // create a circle node
		        Circle node = new Circle(0);
		        
		        // circle shall be ignored by parent layout
		        node.setManaged(false);
		        
		        // randomly pick one of the colors
		        node.setFill(colors[(int) (Math.random() * colors.length)]);
		        
		        // choose a random position
		        node.setCenterX(Math.random() * scene.getWidth());
		        node.setCenterY(Math.random() * scene.getHeight());
		        
		        // add the container to the circle container
		        container.getChildren().add(node);

		        // create a timeline that fades the circle in and and out and also moves
		        // it across the screen
		        Timeline timeline = new Timeline(
		                new KeyFrame(
		                        Duration.ZERO,
		                        new KeyValue(node.radiusProperty(), 0),
		                        new KeyValue(node.centerXProperty(), node.getCenterX()),
		                        new KeyValue(node.centerYProperty(), node.getCenterY()),
		                        new KeyValue(node.opacityProperty(), 0)),
		                new KeyFrame(
		                        Duration.seconds(5 + Math.random() * 5),
		                        new KeyValue(node.opacityProperty(), Math.random()),
		                        new KeyValue(node.radiusProperty(), Math.random() * 20)),
		                new KeyFrame(
		                        Duration.seconds(10 + Math.random() * 20),
		                        new KeyValue(node.radiusProperty(), 0),
		                        new KeyValue(node.centerXProperty(), Math.random() * scene.getWidth()),
		                        new KeyValue(node.centerYProperty(), Math.random() * scene.getHeight()),
		                        new KeyValue(node.opacityProperty(), 0))
		        );

		        // timeline shall be executed once
		        timeline.setCycleCount(1);
		        
		        // when we are done we spawn another node
		        timeline.setOnFinished(evt -> {
		            container.getChildren().remove(node);
		            spawnNode(scene, container);
		        });

		        // finally, we play the timeline
		        timeline.play();
		    }
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
		  
 
	}

