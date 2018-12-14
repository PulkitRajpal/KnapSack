
public class KnapSack {
	public static void main(String[] args) 
		    {
		        String str = "ABDEFGABEF";
		        int len = longestUniqueSubsttr(str);
		        System.out.println("The length of "
		                + "the longest non repeating character is "+len);
		    
	} public static int NO_OF_CHARS = 256;
	     
	 public static int longestUniqueSubsttr(String str)
	    {
	        int n = str.length();
	        int cur_len = 1;    // length of current substring
	        int max_len = 1;    // result
	        int prev_index;        //  previous index
	        int i;
	        int visited[] = new int[NO_OF_CHARS];
	      
	        for (i = 0; i < NO_OF_CHARS; i++) {
	            visited[i] = -1;
	        }
	        
	        visited[str.charAt(0)] = 0;
	    
	        for(i = 1; i < n; i++)
	        {
	            prev_index = visited[str.charAt(i)];
	             
	            
	            if(prev_index == -1 || i - cur_len > prev_index)
	                cur_len++;
	             
	            
	            else
	            {
	                if(cur_len > max_len)
	                    max_len = cur_len;
	                 
	                cur_len = i - prev_index;
	            }
	             
	            visited[str.charAt(i)] = i;
	        }
	         
	        if(cur_len > max_len)
	            max_len = cur_len;
	         
	        return max_len;
	    }
	     
	   
	}

