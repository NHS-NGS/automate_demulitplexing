# automate_demulitplexing

* This script is designed to be run as a cron job on the hour on a linux workstation.

* It loops through each run folder on the share to which the nextseq writes/copies the runfolder.

* Illumina runs are marked as complete by the presense of a RTAComplete.txt file.

* The script looks to check if this file is present, the run hasn't been demultiplexed before - defined by the presence of a 'demultiplex.txt' log file and the presense of a worksheet.

* Before running bcl2fastq it performs a test, ensuring the bcl2fastq is installed.

* If all of these conditions are met it runs bcl2fastq. The standard out and standard error is recorded to the 'demultiplex.txt' file (which also serves to mark when a run has been demultiplexed or not).

* Throughtout the script a 'cron job' log file is used to record the decision making - if and why a run folder was or was not demultiplexed and the results of various tests. 

* Email messages are sent to record progress and the smartsheet API is used to record OPMS data. (you can ignore or update this code as suits)
