# Problem Solving Level3

## 1 - Write a program to fill a 3*3 matrix with random numbers.


            #include <ctime>
            #include <iostream>
            #include <string>
            #include <cstdlib> // For rand and srand
            #include <ctime>   // For time function
            using namespace std;
            
            int RandomNumber(int from, int to) {
            	int RandNum = rand() % (to - from + 1) + from;
            	return RandNum;
            }
            void FillMetrix(int x[][3], int from, int to) {
            
            	for (int i = 0; i < 3; i++) {
            		for (int j = 0; j < 3; j++) {
            			x[i][j] = RandomNumber(from, to);
            		}
            	}
            }
            void PrintMetrix(int x[][3]) {
            
            	for (int i = 0; i < 3; i++) {
            		for (int j = 0; j < 3; j++) {
            			cout << x[i][j] << "    ";
            		}
            		cout << endl;
            	}
            }
            int main() {
            	int x[3][3];
            
            	srand((unsigned)time(NULL));
            
            	FillMetrix(x, 1, 100);
            
            
            	PrintMetrix(x);
            
            	return 0;
            
            }

## 2 - Write a program to fill a 3*3 matrix with random numbers, then print each row sum:--

        #include <ctime>
        #include <iostream>
        #include <string>
        #include <cstdlib> // For rand and srand
        #include <ctime>   // For time function
        using namespace std;
        
        int RandomNumber(int from, int to) {
        	int RandNum = rand() % (to - from + 1) + from;
        	return RandNum;
        }
        void FillMetrix(int x[][3]) {
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			x[i][j] = RandomNumber(1, 100);
        		}
        	}
        }
        void CalcRows(int x[][3]) {
        
        	int counter = 0;
        
        	cout << "Result of Rows Sum :" << endl;
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			counter += x[i][j];
        		}
        		cout << "Row(" << i << ") : " << counter << endl;
        		counter = 0;
        	}
        }
        void PrintMetrix(int x[][3]) {
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			cout << x[i][j] << "    ";
        		}
        		cout << endl;
        	}
        }
        int main() {
        	int x[3][3];
        
        	srand((unsigned)time(NULL));
        
        	FillMetrix(x);
        	PrintMetrix(x);
        
        	CalcRows(x);
        
        	return 0;
        
        }
## 3 - another solution:-

        #include <ctime>
        #include <iostream>
        #include <string>
        #include <cstdlib> // For rand and srand
        #include <ctime>   // For time function
        using namespace std;
        
        int RandomNumber(int from, int to) {
        	int RandNum = rand() % (to - from + 1) + from;
        	return RandNum;
        }
        void FillMetrix(int x[][3]) {
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			x[i][j] = RandomNumber(1, 100);
        		}
        	}
        }
        int CalcRows(int x[][3]) {
        
        	int counter = 0;
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			counter += x[i][j];
        		}
        		return counter;
        	}
        }
        void PrintMetrix(int x[][3]) {
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			cout << x[i][j] << "    ";
        		}
        		cout << endl;
        	}
        }
        void PrintEachRow(int x[][3] ) {
        	cout << " \n Result of Rows Sum :\n" << endl;
        	for (int i = 0; i < 3; i++) {
        		cout << "Row(" << i+1 << ") sum : " << CalcRows(x)<< endl;
        	}
        }
        int main() {
        	int x[3][3];
        
        	srand((unsigned)time(NULL));
        
        	FillMetrix(x);
        	PrintMetrix(x);
        
        	CalcRows(x);
        	PrintEachRow(x);
        	return 0;
        
        }

## 4 -Write a program to fill a 3*3 matrix with random numbers, then sum each row in a separate array and print the result:-


          #include <ctime>
          #include <iostream>
          #include <string>
          #include <cstdlib> // For rand and srand
          #include <ctime>   // For time function
          using namespace std;
          
          int RandomNumber(int from, int to) {
          	int RandNum = rand() % (to - from + 1) + from;
          	return RandNum;
          }
          void FillMetrix(int x[][3]) {
          
          	for (int i = 0; i < 3; i++) {
          		for (int j = 0; j < 3; j++) {
          			x[i][j] = RandomNumber(1, 100);
          		}
          	}
          }
          int CalcRows(int x[][3], int arr[]) {
          
          	for (int i = 0; i < 3; i++) {
          		  arr[i] = 0; // Initialize the sum for each row
          		for (int j = 0; j < 3; j++) {
          			arr[i] += x[i][j];
          		}
          	}
          }
          void PrintMetrix(int x[][3]) {
          
          	for (int i = 0; i < 3; i++) {
          		for (int j = 0; j < 3; j++) {
          			cout << x[i][j] << "    ";
          		}
          		cout << endl;
          	}
          }
          void PrintEachRow(int arr[]) {
          	cout << " \n Result of Rows Sum :\n" << endl;
          	for (int i = 0; i < 3; i++) {
          		cout << "Row" << i + 1 << " sum : " << arr[i] << endl;
          	}
          }
          int main() {
          	int x[3][3];
          	int arr[3];
          	srand((unsigned)time(NULL));
          
          	FillMetrix(x);
          	PrintMetrix(x);
          
          	CalcRows(x, arr);
          	PrintEachRow(arr);
          
          	return 0;
          
          }

## 5 - Write a program to fill a 3*3 matrix with random numbers, then sum each col in another array and print them:-


      #include <ctime>
      #include <iostream>
      #include <string>
      #include <cstdlib> // For rand and srand
      #include <ctime>   // For time function
      using namespace std;
      
      int RandomNumber(int from, int to) {
      	int RandNum = rand() % (to - from + 1) + from;
      	return RandNum;
      }
      void FillMetrix(int arr[3][3] , short Rows , short Cols) {
      
      	for (short i = 0; i < Rows; i++) {
      		for (short j = 0; j < Cols; j++) {
      			arr[i][j] = RandomNumber(1, 100);
      		}
      	}
      }
      void PrintMetrix(int arr[3][3] , short Rows , short Cols) {
      
      	for (short i = 0; i < Rows; i++) {
      		for (short j = 0; j < Cols; j++) {
      			cout << arr[i][j] << "    ";
      		}
      		cout << endl;
      	}
      }
      int ColSum(int arr[3][3], short Rows , short colNum) {
      
      	int sum = 0;
      	for (int i = 0; i < Rows - 1; i++)
      	{
      		sum += arr[i][colNum];
      	}
      	return sum;
      }
      void SumMaterix(int arr[3][3] ,int arr2[] , short Rows, short Cols ) {
      	for (short x = 0; x < Cols; x++)
      	{
      		arr2[x] = ColSum(arr, Rows, x);
      	}
      }
      void PrintEachColSum( int arr2[3] , short Length ) {
      	cout << " \n Result of Rows Sum :\n" << endl;
      	for (short j = 0; j < Length; j++) {
      		cout << "Row" << j + 1 << " sum : " << arr2[j] << endl;
      	}
      }
      int main() {
      
      	srand((unsigned)time(NULL));
      
      	int arr[3][3];
      	int arr2[3];
      
      
      	FillMetrix(arr ,3,3);
      	PrintMetrix(arr,3,3);
      
      	SumMaterix(arr, arr2,3,3);
      	PrintEachColSum(arr2,3);
      
      	return 0;
      
      }


## 6 - 






            
