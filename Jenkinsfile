import org.jenkinsci.plugins.pipeline.utility.steps.fs.FileWrapper

def oldB = T26.0_PDM
def newB = T26.1_PDM


pipeline{
  stages{
    stage('Checkout PSF Folder'){
      steps{
        dir(psf){
            script{
              def files = findFiles glob:'*.psf'
              findANdReplaceInFiles(files, oldB, newB)
            }
        }
      }
    }
  }
}

void findANdReplaceInFile(filePath, String search, String replace){
  def fileText 
  fileText = readFile file:filePath
  fileText = fileText.replaceAll(search, replace)
  writeFile file:filePath, text:fileText
}

void findANdReplaceInFiles(FileWrapper[] files, String search, String replace){
  for(fileWrapper in files){
    findANdReplaceInFile(fileWrapper.path, search, replace)
  }
}


    
