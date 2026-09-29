# Subscription-manager
simple and efficient subscription manager
def subscription_manager_list():
    subscriptions = []
    
    print(" Welcome to your Basic Subscription Manager (List Version)! ")
    print("Enter 'done' for the subscription name when finished adding.")
    print("-" * 45)

    
    while True:
        
        sub_name = input("Enter subscription name (or 'done'): ").strip()
        
        
        if sub_name.lower() == 'done':
            break
        
        
        while True:
            try:
                sub_cost_str = input(f"Enter cost for '{sub_name}' (e.g., 9.99): $").strip()
                
                sub_cost = float(sub_cost_str)
                
                if sub_cost < 0:
                    print("Cost cannot be negative. Please enter a positive value.")
                else:
                    break  
            except ValueError:
                
                print("Invalid input. Please enter a valid number for the cost.")

        
        subscription_entry = [sub_name, sub_cost]
        subscriptions.append(subscription_entry)
        
        print(f"Added: {sub_name} (${sub_cost:.2f})\n")
    
    
    print("\n" + "=" * 45)
    
    if not subscriptions:
        print(" No subscriptions were entered.")
        print("=" * 45)
        return

    
    total_cost = 0.0
    
    print(" Your Subscriptions:")
    for entry in subscriptions:
        
        name = entry[0]  
        cost = entry[1]  
        
        total_cost += cost
        
        
        print(f"- {name}: ${cost:.2f}")

    print("-" * 45)
   
    print(f" Total Monthly Cost: ${total_cost:.2f}")
    print("=" * 45)
subscription_manager_list()
