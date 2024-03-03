struct ListNode* reverseBetween(struct ListNode* start, int a, int b)
{
    a-=1;
    b-=1;
    struct ListNode *node1=NULL,*node2=NULL,*nodeb=NULL,*nodea=NULL,*ptr=start;
    int c=0;
    while(ptr!=NULL)
    {
        if(c==a-1)
            nodeb=ptr;
        else if(c==a)
            node1=ptr;
        else if(c==b)
            node2=ptr;
        else if(c==b+1)
            {
                nodea=ptr;
                break;
            }
        c+=1;
        ptr=ptr->next;
    }
    struct ListNode*pre=nodea,*temp;
    ptr=start;
    c=0;
    
    while(ptr!=NULL)
    {   
        if(c>=a && c<b)
        {
            temp=ptr->next;
            ptr->next=pre;
            pre=ptr;
            ptr=temp;
            
        }
        else if(c==b)
        {
            ptr->next=pre;
            if(a==0)
                start=ptr;
            else
                nodeb->next=ptr;
            
            
            break;
        }
        else
            ptr=ptr->next;
        c+=1;
        
        
    }
    return start;
}
