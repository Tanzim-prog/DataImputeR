# DataImputeR
setwd("~/DS/") 
data_2 <- read.csv("~/DS/Dataset_2.csv")
print(data_2)
no_of_missing_values = colSums(is.na(data_2))
no_of_missing_values
missing_values_of_room = which(is.na(data_2$Rooms))
missing_values_of_room
missing_values_of_type = which(is.na(data_2$Type))
missing_values_of_type
missing_values_of_price = which(is.na(data_2$Price))
missing_values_of_price
data_2$Price[c(18)]<- NA
data_2
data_2$Type <- factor(data_2$Type, levels=c("h", "m", "l"), labels=c(1,2,3))
data_2
remove_missing_values = na.omit(data_2)
remove_missing_values
room_mean_value = mean(data_2$Rooms, na.rm = T)
recover_room_missing_value = data_2$Rooms[is.na(data_2$Rooms)] <- room_mean_value
recover_room_missing_value
data_2
price_mean_value = mean(data_2$Price, na.rm = T)
recover_price_missing_value = data_2$Price[is.na(data_2$Price)] <- price_mean_value
recover_price_missing_value
data_2
room_median_value = median(data_2$Rooms, na.rm = T)
recover_room_missing_value = data_2$Rooms[is.na(data_2$Rooms)] <- room_median_value
recover_room_missing_value
data_2
price_median_value = median(data_2$Price, na.rm = T)
recover_price_missing_value = data_2$Price[is.na(data_2$Price)] <- price_median_value
recover_price_missing_value
data_2
mode <- function (a)
  {
  b <- unique(a)
  tab <- tabulate (match(a,b))
  b[tab == max (tab)]
  }
room_mode_value = mode(data_2$Rooms)
recover_room_missing_value = data_2$Rooms[is.na(data_2$Rooms)] <- room_mode_value
recover_room_missing_value
data_2
price_mode_value = mode(data_2$Price)
recover_price_missing_value = data_2$Price[is.na(data_2$Price)] <- price_mode_value
recover_price_missing_value
data_2
