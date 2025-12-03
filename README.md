# REGISTRATION-CERTIFICATE-DETAILS
#include <stdio.h>
#include <string.h>

struct vehicledetails{
    char vehicleno[11];
    char owner[10];
    char vehiclename[10];
    char registered_RTO[20];
};

int main() {
struct vehicledetails v[5] = {
        {"MH42BB2872","SOHAM","SWIFT","BARAMATI"},
        {"MH42AA0001","OM","DZIRE","BARAMATI"},
        {"MH12SS1000","AMRUT","I10","PUNE"},
        {"MH12FF1001","SAHIL","I20","PUNE"},
        {"MH14EE2222","OJAS","ALTO","PIMPARI"}
    };

  printf("RC details:\n");
    printf("%-15s %-15s %-15s %-15s\n",
           "vehicleno", "owner", "vehiclename","registered_RTO");
    printf("-----------------------------------------------------------------------\n");

  for (int i = 0; i < 5; i++) {
        printf("%-15s %-15s %-15s %-15s\n",
               v[i].vehicleno, v[i].owner, v[i].vehiclename ,v[i].registered_RTO);
    }


   char searchNo[15];
    int found = 0;
    int not_found=1;
    printf("\nEnter vehicle number to search: ");
    scanf("%s",searchNo);

  for(int i = 0; i < 5; i++) {
        if(strcmp(v[i].vehicleno, searchNo) == 0) {
            printf("\nVehicle Found!\n");
            printf("Vehicle No     : %s\n", v[i].vehicleno);
            printf("Owner Name     : %s\n", v[i].owner);
            printf("Vehicle Name   : %s\n", v[i].vehiclename);
            printf("Registered RTO : %s\n", v[i].registered_RTO);
            found = 1;
            break;
        }
    }

   if(not_found) {
        printf("\nNo vehicle found with number: %s\n", searchNo);
    }

  return 0;
}
