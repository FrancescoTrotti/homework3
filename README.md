# Homework3

# Corso ciberfisico univr

- Autore: Francesco Trotti

- Data: 6/06/2018

# Prerequisiti

Pangolin installato.<br>
Librerie OpenCv installate <br>
ORB_SLAM2 installato <br>

# Esecuzione:

Per eseguire il progetto clonare questa repository da gitHub con il comando "git clone https://github.com/FrancescoTrotti/homework3.git" nella cartella "catkin_ws/src".<br>
Spostarsi nella directory "ORB_SLAM2/pcl/bin" ed eseguire "./clustering" per visualizzare la nuvola di punti clusterizzata.
Se si vuole eseguire completamente ORB_SLAM è necessario andare nella cartella ORB_SLAM2/src e sostituire il file "System.cc" 
scaricato.<br>
In seguito andare nella directory ORB_SLAM2/include ed aggiungere la dichiarazione della fiunzione "void SaveMapPoints(const string &filename);" nel file "System.h" <br>
Andare nella directory ORB_SLAM2/Examples/ROS/ORB_SLAM2/src ed aggiungere la chiamata a funzione "SLAM.SaveMapPoints("MapPointsSave.txt");" sotto "ros::spin();" nel file ros_stereo.cc <br>
Una volta volta sostituito tutto andare nella directory ORB_SLAM ed eseguire il comando "./build.sh" e di seguito "./build_ros.sh"<br>
Per eseguire ORB_SLAM2 è necessario lanciare:
- roscore su un terminale <br>
- rosrun ORB_SLAM2 Stereo Vocabulary/ORBvoc.txt Examples/Stereo/EuRoC.yaml true <br>
- rosbag play PATH/V1_01_easy.bag /cam0/image_raw:=/camera/left/image_raw /cam1/image_raw:=/camera/right/image_raw (dove PATH va sostituito con il percorso del file .bag, finito di eseguire la bag premere "Ctrl-c" per esportare il file .txt) <br>
Andare nella directory pcl scaricata e ed eseguire il cmake per convertire il file .txt in .pcd e per compilre il codice per il clustering.
Andare nella cartella pcl/bin ed eseguire "./clustering" <br>

# Progettazione:

Nella progettazione dell'homework3 è stato modificato il codice "System.cc", il quale si trova nella directory src di ORB_SLAM2, introducendo una funzione (void System::SaveMapPoints(const string &filename)) che esporta le coordinate (x,y,z) della nuvola di punti in un file .txt. <br>
Di seguito è stato implementato un codice "xyzTopcd.cpp" che converte il file .txt in .pcd. <br>
Infine sono stati modificati i parametri del file "clustering.cpp" in modo tale da rappresentare al moglio possibile le nuvole di punti. <br> 

#Immagini dimostartive:



