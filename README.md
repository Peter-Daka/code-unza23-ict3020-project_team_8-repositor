


# code-unza23-ict3020-project_team_8-repositor
#This repository is for the AUTOSCIDL System

// java source code for the a feature of the AUTOSCIDL 





import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.URL;
import java.net.URLConnection;

public class JctrFreshContent {

    /**
     * @return
     * @throws IOException
     */
    public static String getFreshContent() throws IOException {
        URL url = new URL("https://www.jctr.org.zm/");
        URLConnection connection = url.openConnection();
        BufferedReader reader = new BufferedReader(new InputStreamReader(connection.getInputStream()));

        StringBuilder contentBuilder = new StringBuilder();
        String line;
        while ((line = reader.readLine()) != null) {
            contentBuilder.append(line);
        }
        reader.close();

        return contentBuilder.toString();
    }

    /**
     * @param args
     * @throws IOException
     */
    public static void main(String[] args) throws IOException {
        String freshContent = getFreshContent();

        // Do something with the fresh content, such as printing it to the console or saving it to a file.
        System.out.println(freshContent);
    }

    @Override
    public String toString() {
        return "JctrFreshContent []";
    }

}

