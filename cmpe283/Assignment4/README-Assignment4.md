# Assignment 4: Shadow Paging vs Nested Paging 

 

##  1) WORK DISTRIBUTION 

### Sarat Kumar Kaniti 
  * Verified that Assignment III code is functional. 
  * Ran assignment 3 code and took output for Nested paging  
  * Tested and verified the results
  * Documented the steps and results 

### Srikanth Nimmagadda 
  * Switched KVM to shadow paging (ept=0) 
  * Ran assignment 3 code and took output for Shadow Paging  
  * Tested and verified the results 
  * Documented the steps and results 
  
 Together we analyzed the output and answered the questions 
 
 ## 2) Output screenshots: 
###  Nested Paging 
### Before reboot 
![alt text](https://github.com/sarat458/linux/blob/bd5e0f92cc34fd6a4f3685ad6a9149f5d8b8d781/cmpe283/Assignment4/output/ass4-1.png "img1")
![alt text](https://github.com/sarat458/linux/blob/bd5e0f92cc34fd6a4f3685ad6a9149f5d8b8d781/cmpe283/Assignment4/output/ass4-2.png "img2")

### After reboot 
![alt text](https://github.com/sarat458/linux/blob/bd5e0f92cc34fd6a4f3685ad6a9149f5d8b8d781/cmpe283/Assignment4/output/ass4-3.png "img3")
![alt text](https://github.com/sarat458/linux/blob/bd5e0f92cc34fd6a4f3685ad6a9149f5d8b8d781/cmpe283/Assignment4/output/ass4-4.png "img4")

### Shadow Paging 
### Before reboot 
![alt text](https://github.com/sarat458/linux/blob/bd5e0f92cc34fd6a4f3685ad6a9149f5d8b8d781/cmpe283/Assignment4/output/ass4-6.png "img6")
![alt text](https://github.com/sarat458/linux/blob/bd5e0f92cc34fd6a4f3685ad6a9149f5d8b8d781/cmpe283/Assignment4/output/ass4-7.png "img7")

### After reboot 
![alt text](https://github.com/sarat458/linux/blob/bd5e0f92cc34fd6a4f3685ad6a9149f5d8b8d781/cmpe283/Assignment4/output/ass4-8.png "img8")
![alt text](https://github.com/sarat458/linux/blob/bd5e0f92cc34fd6a4f3685ad6a9149f5d8b8d781/cmpe283/Assignment4/output/ass4-9.png "img9")
 
 
##  3)What did you learn from the count of exits? Was the count what you expected? If not, why not? 
The total number of exits in shadow paging is more when compared to nested paging. The reason behind this nested paging will do only VM exit whenever an EPT violation occurs. But in shadow paging, when VM executes CR0, CR3, CR4, or any other related exits, it can exit every time. 

## 4)What changed between the two runs (ept vs no-ept)? 
### EPT Mode 
There is no need to exit in EPT mode as the translation from guest VM to guest PA to host PA is done with a two-layer page table and more page access is required. So then the guest VM has to own the page table and so the operation on CR3 is done natively. 

### No EPT Mode 
In shadow paging, the guest VM does not own the page table. So to do this CR3 should be simulated by the VMM. 
