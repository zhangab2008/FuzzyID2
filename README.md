# FuzzyID2
FuzzyID2: A software package for large dataset species identification via barcoding and metabarcoding using Hidden Markov Models and fuzzy set methods

# This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
# The following restriction to the GNU GPL applies: contact the author of this program (http://willpearse.github.com/phyloGenerator) for a suitable citation when publishing work that uses this code.
# This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.
# You should have received a copy of the GNU General Public License along with this program.  If not, see <http://www.gnu.org/licenses/>.
###

FuzzyID2 installation:
  x86_64 compile command:
    g++ main.cpp mainFunction.cpp commonFunction.cpp -o FuzzyID2_x86_64 -lsqlite3 -lbpp-core -lbpp-seq -lbpp-phyl -Wl,-rpath ./lib64 -L ./lib64 -I ./include
    ln -s FuzzyID2_x86_64 FuzzyID2

  i686 compile command:
    g++ main.cpp mainFunction.cpp commonFunction.cpp -o FuzzyID2_i686 -lsqlite3 -lbpp-core -lbpp-seq -lbpp-phyl -Wl,-rpath ./lib -L ./lib -I ./include
    ln -s FuzzyID2_i686 FuzzyID2

FuzzyID2 execute commands:
    (1)reference database construction
        python3 FuzzyID2_makeDB.py
        #parameters should be set in config file(config.txt)
    (2)sequence identification
        1)single marker 
            ./FuzzyID2 -c ID -in ./test/Noc_COI.fas -m K2P -out ./test/Noc-out.txt -d Noctuidae
        2)metabarcode markers
            ./FuzzyID2 -c ID -in ./test/query_metabarcode.fas -m K2P -out ./test/Metabarcode_out.txt -d Metabarcode
        3)Plant markers
            ./FuzzyID2 -c ID -in ./test/query_rbcl.fas+./test/query_trnl.fas -m K2P -out ./test/Plant_out.txt -d Plant -rb rbcl -mb trnl

#For more information, please read the FuzzyID2-guide.pdf. 
