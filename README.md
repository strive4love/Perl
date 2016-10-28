## handleFileByLine.pl
#!/usr/bin/perl -w

use strict ;

####
$^I = ".back";
while (<>) {
	#chomp;
	#how to relove the curent line?	
	#s/\s+//g;
	######################
    #s/,/\n/g;
	#####################
	#s/^\s?COM\.//g;
	#s/\s+$/\n/g;
	#####################
	s/DM_TRNRP_PL3_REP PL3/DM_TRN_CUR_PL3_REP PL3/g; 
	s/and PL3.M_TRN_GTYPE in (.+)//g;
	print;
}


## sortFileContent.pl
#!/usr/bin/perl
use warnings;
use strict;

my $inFileName = $ARGV[0] or die "Need to specify a file on the command line\n";
my $outFileName = $ARGV[0].'_sort';

open INFILE,$inFileName;
open OUTFILE,'>',$outFileName;

my @a=<INFILE>;
my @result;

@result= sort {$a cmp $b}  @a;
close INFILE;

foreach (@result){
   print OUTFILE;  
}
close OUTFILE;


