users=[]

class user_profile:
    def __init__(self,name,email,password,phone_no):
        self.name=name
        self.email=email
        self.password=password
        self.phone_no=phone_no
        my_dict={}
        my_dict['name']=name
        my_dict['email']=email
        my_dict['password']=password
        my_dict['phone_no']=phone_no
        users.append(my_dict)
    
    def validate(self,email,password):
        for user in users: #validation process
            if user['email']==email and user['password']==password:
                return True
                break
            else:
                print("Invalid User Credentials")
                return False
    
if __name__== '__main__':
    while True: #main loop for login purpuse 
        print("Choose an option: 1. Register 2. Login 3.Exit")
        sol=int(input("Enter an Option:"))
        if(sol==1):
            name=input("Enter your Name:")
            email=input("Enter your Email:")
            password=input("Enter Password:")
            phone_number=int(input("Enter your Phone Number:"))
            user=user_details(name,email,password,phone_number)
            print("You have registered successfully...")
            temp1=input("Enter your registered mailid:")
            temp2=input("Enter your password:")
            val=user.validate(temp1,temp2)
        elif(sol==2):
            temp1=input("Enter your registered mailid:")
            temp2=input("Enter your password:")
            def validate(email,password):
                for user in users:
                    if user['email']==email and user['password']==password:
                        return True
                        break
                    else:
                        print("Invalid User Credentials")
                        return False
            val=validate(temp1, temp2)
        else:
            print("Thank you")
            break
            
        if val:
            print("You successfully logged in..")
            print("Here is the List of services:")
            print("1.Available Services  2.Cancel a service  3.Exit")
            choice=int(input("Enter your Choice:"))
            #list of services and their cost
            if(choice==1): #Booking a service
                Location=input("Enter the Nearby Location:")
                Date=input("Enter a Date:")
                print("Choose the service: 1.Electrical: $1000  2.Plumbing: $1100  3.Carpeting: $900  4.Beauty: $500  5.Cleaning: $1500")
                option=int(input("Enter your Choice:"))
                if(option==1):
                    category="Electrical"
                    amount='$1000'
                    print(category,amount)
                    
                elif(option==2):
                    category="Plumbing"
                    amount='$1100'
                    print(category,amount)
                
                
                elif(option==3):
                    category="Carpeting"
                    amount='$900'
                    print(category,amount)

                elif(option==4):
                    category="Beauty"
                    amount='$500'
                    print(category,amount)
                
                elif(option==5):
                    category="Cleaning"
                    amount='$1500'
                    print(category,amount)

                else:
                    print("Choose a avilable services only")                

                
                print("Booked Successfully... ")

            elif(choice==2): #Cancelling a service
                email=input("Enter your Email:")
                for user in users:
                    if user['email']==email:
                            print("Do you want to cancel the services?")
                            answer=input("yes/no:")
                            if answer=='yes':
                               print("Your Services has been Waiting to Cancel.....")
                print("Cancelled Successfuly.. ")
                print("Amount will be returned shortly..")
                    
            else:
                    print("Invalid mail id")
        else:
                    print("Thank you")
                    break
