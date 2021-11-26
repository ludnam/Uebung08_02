# Uebung08_02

package org.hsd.inflab.Uebung08;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.canvas.Canvas;
import javafx.scene.canvas.GraphicsContext;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Polygon;
import javafx.scene.shape.Rectangle;
import javafx.stage.Stage;


public class App extends Application {

    @Override
    public void start(Stage stage) {
        
    	try {
    		
    		BorderPane fenster = new BorderPane();
    		Scene buehne = new Scene(fenster,600,600);
    		
    		Canvas canvas = new Canvas(600,600);
    		GraphicsContext gc = canvas.getGraphicsContext2D();
    		
    		double xPolygon[] = {200,400,200,400,200,200,300,400,400,200};
    		double yPolygon[] = {400,200,200,400,400,200,100,200,400,400};
    		double xPolygonQuadrat[] = {200,400,400,200,200};
    		double yPolygonQuadrat[] = {400,400,200,200,400};
    		double xPolygonDreieck[] = {200,400,300,200};
    		double yPolygonDreieck[] = {200,200,100,200};
    		
    		gc.setFill(Color.RED);
    		gc.fillPolygon(xPolygonQuadrat, yPolygonQuadrat,xPolygonQuadrat.length);
    		
    		gc.setFill(Color.RED);
    		gc.fillPolygon(xPolygonDreieck, yPolygonDreieck,xPolygonDreieck.length);
    		
    		gc.setStroke(Color.BLACK);    		
    		gc.strokePolygon(xPolygon, yPolygon,xPolygon.length);
    		
    		fenster.getChildren().add(canvas);
    		
    		stage.setTitle("Das Haus Vom Nikolaus");
    		stage.setScene(buehne);
    		stage.show();
    		
    	}
    	catch (Exception e) {
    		e.printStackTrace();    		
    	}
    }

    public static void main(String[] args) {
        launch();
    }

}
