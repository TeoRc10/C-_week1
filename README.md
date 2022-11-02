# TD_Cs_11_10

using System;

namespace TD_Index_Cs_11_10
{
    class Program
    {
        static void Main(string[] args)
        {
            var tempRecord = new TempRecord();

            tempRecord[3] = 58.3F; // Use the indexer's set accessor
            tempRecord[5] = 60.1F;

            for (int i = 0; i < 10; i++)  // Use the indexer's get accessor
            {
                Console.WriteLine("$Element#{i} = {tempRecord[i]");   // $ permet d'optimiser l'affichage
            }

            Console.WriteLine("Press any key to exit");
            Console.ReadKey();


            var week = new DayCollection();
            Console.WriteLine(week["Fri"]);

            try     // The try-catch statement consists of a try block followed by one or more catch clauses, which specify handlers for different exceptions. When an exception is thrown, the common language runtime looks for the catch statement that handles this exception
            {
                Console.WriteLine(week["Made-up day"]);
            }
            catch(ArgumentOutOfRangeException e)
            {
                Console.WriteLine($"Not supported input:{e.Message}");
            }

            MyClass2 object_cl2 = new MyClass2();
            /*MyDelegate d = object_cl2.createDelegate();*/
            MyClass3 object_cl3 = new MyClass3();
            /*object_cl3.callDelegate(d, "Calling the delegate");*/

            System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");
            Console.WriteLine(di.TotalFreeSpace);
            Console.WriteLine(di.VolumeLabel);

            System.IO.DirectoryInfo dirInfo = di.RootDirectory;
            Console.WriteLine(dirInfo.Attributes.ToString());

            // Get the subdirectories directly that is under the root
            System.IO.DirectoryInfo[] dirInfos = dirInfo.GetDirectories("*.*");
            foreach(System.IO.DirectoryInfo d in dirInfos)
            {
                Console.WriteLine(d.Name);
            }

            // Get the current application directory

            string currentDirName = System.IO.Directory.GetCurrentDirectory();
            Console.WriteLine(currentDirName);

            // Get the files in the directory and print out some information about them

            System.IO.FileInfo[] fileNames = dirInfo.GetFiles("*.*");

            foreach (System.IO.FileInfo fi in fileNames)
            {
                Console.WriteLine("{0};{1};{2}", fi.Name, fi.LastAccessTime, fi.Length);
            }

            string folderName = "folder_level1";
        }
    }
}
