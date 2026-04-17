import org.apache.poi.xslf.usermodel.*;
import java.io.FileOutputStream;
import java.io.File;

public class QuizPitagoras {
    public static void main(String[] args) throws Exception {
        XMLSlideShow ppt = new XMLSlideShow();
        
        // Criar Slide de Capa
        XSLFSlide slide1 = ppt.createSlide();
        XSLFTextBox title = slide1.createTextBox();
        title.setText("Quiz: Teorema de Pitágoras");
        
        // Criar Slide de Questão
        XSLFSlide slide2 = ppt.createSlide();
        XSLFTextBox question = slide2.createTextBox();
        question.setText("Questão 1: Catetos 6 e 8. Qual a hipotenusa?");
        
        // Configurar as alternativas (Botões seriam formas aqui)
        XSLFAutoShape btnA = slide2.createAutoShape(ShapeType.RECT);
        btnA.setText("a) 10 cm");
        // Nota: A configuração de sons e ações é feita via XML no Apache POI
        
        // Salvar o arquivo
        FileOutputStream out = new FileOutputStream("QuizPitagoras.pptx");
        ppt.write(out);
        out.close();
        
        System.out.println("Arquivo Power Point criado com sucesso!");
    }
}
# Eletiva-Fundamentos-da-Matem-tica-
