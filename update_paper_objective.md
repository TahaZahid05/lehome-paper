Our updated projects objective:


1) Tried the following models: DP, ACT, Smolvla, XVLA, pi0.5, 
2) Added augemntations
3) Added colorized depth
4) Tried PEFT for pi0.5 and smolvla to train vlm as well.
5) Found ACT + AUG + DEPTH was the best configuration (generalization wise and average wise)
6) Analysis on trying different chunk_size and n_action_steps of ACT to see if that has any effects
7) Wrote code for human in loop augmentation to capture failure cases to better train the model but unfortunately due to lack of gui on hpc, was not able to move ahead with the idea.

Results (I will add more later):

1) DP:
Shared Model	Success %				
top_long	5.00%				
top_short	0.00%			Macro-Average	11.67%
pant_long	3%				
pant_short	38.33%				

2) SmolVLA:
Local Results						
Shared Model	Success %					
top_long	56.67%					
top_short	11.67%			Macro-Average	44.17%	
pant_long	35%					
pant_short	73.33%					
						
						
						
Leaderboard Results						
Shared Model	Success %					
top_long	21.50%					
top_short	8.50%			Macro-Average	34.50%	
pant_long	39.50%					
pant_short	68.50%					
						
						
Unseen Percentages	Unseen_0	Unseen_1	Average			
top_long	60.00%	0.00%	30.00%			
top_short	0.00%	0.00%	0.00%			
pant_long	40.00%	0.00%	20.00%			
pant_short	60.00%	60.00%	60.00%			

3) SmolVLA_Augmentation

Shared Model	Success %					
top_long	55.00%					
top_short	20.00%			Macro-Average	46.67%	
pant_long	30%					
pant_short	81.67%					
						
						
						
Unseen Percentages	Unseen_0	Unseen_1	Average			
top_long	80.00%	40.00%	60.00%			
top_short	60.00%	0.00%	30.00%			
pant_long	90.00%	50.00%	70.00%			
pant_short	20.00%	60.00%	40.00%			


4) SmolVLA_Augmentation_PEFT

Shared Model	Success %				
top_long	65.00%				
top_short	28.33%			Macro-Average	53.75%
pant_long	43%				
pant_short	78.33%				
					
					
Unseen Percentages	Unseen_0	Unseen_1	Average		
top_long	90.00%	10.00%	50.00%		
top_short	0.00%	0.00%	0.00%		
pant_long	50.00%	0.00%	25.00%		
pant_short	10.00%	40.00%	25.00%		

5) ACT
Shared Model	Success %				
top_long	75.00%				
top_short	45.00%			Macro-Average	58.96%
pant_long	38%				
pant_short	78.33%				
					
					
					
					
Unseen Percentages	Unseen_0	Unseen_1	Average		
top_long	100.00%	70.00%	85.00%		
top_short	0.00%	60.00%	30.00%		
pant_long	50.00%	10.00%	30.00%		
pant_short	0.00%	90.00%	45.00%		
					
					
					
6) ACT_DEPTH
Shared Model	Success %				
top_long	70.83%				
top_short	50.00%			Macro-Average	61.25%
pant_long	47%				
pant_short	77.50%				
					
					
Unseen Percentages	Unseen_0	Unseen_1	Average		
top_long	100.00%	20.00%	60.00%		
top_short	0.00%	70.00%	35.00%		
pant_long	20.00%	0.00%	10.00%		
pant_short	10.00%	100.00%	55.00%		
					

7) ACT_DEPTH_AUG
Shared Model	Success %				
top_long	61.67%				
top_short	43.33%			Macro-Average	59.79%
pant_long	50%				
pant_short	84.17%				
					
					
Unseen Percentages	Unseen_0	Unseen_1	Average		
top_long	80.00%	10.00%	45.00%		
top_short	0.00%	70.00%	35.00%		
pant_long	90.00%	50.00%	70.00%		
pant_short	20.00%	90.00%	55.00%		
					
					