XRP Ledger
This illustrates the use of Apache JMeter in building an API which provides with the information on the transactions recorded in the XRP Ledger.
Installation
Install Java 8+ on Windows/Linux systems.
Download and install Apache Jmeter 5.1.1 release from the Apache site
For Linux systems (Ubuntu) – wget  https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-5.1.tgz 

For Windows systems – https:// https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-5.1.tgz

Execution

On Linux systems abd Windows (using CLI)
Place the API_ripple.jmx file inside the cd bin folder of the Apache Jmeter main folder.
Run the below command in the bin folder
Jmeter –n –t API_ripple.jmx –l result.jtl

This will execute the script generating the result file stored under ‘result.jtl’ and ‘data.dat’ generated in the bin folder.

Plot Gnuplot graph
Install gnuplot (in Ubuntu)
sudo apt-get install gnuplot-x11
Run the below command to plot the graph
gnuplot> set xdata time
gnuplot> set timefmt x “%Y-%b-%d %H:%M:%S”
gnuplot> set datafile separator “,”
gnuplot> set xlabel “time”
gnuplot> set ylabel “Sequence number”
gnuplot> set title “Time vs Sequence number”
gnuplot> plot “data.dat” using 1:2 with linespoints

Real time Gnuplot
To make the graph plot in real time
Create a file as ‘realtime.p’
 Enter the below command
set xdata time
set timefmt x “%Y-%b-%d %H:%M:%S”
set datafile separator “,”
set xlabel “time”
set ylabel “Sequence number”
set title “Time vs Sequence number”
plot “data.dat” using 1:2 with linespoints
reread
Run the below command in the command prompt/terminal
Gnuplot> load ‘realtime.p’

