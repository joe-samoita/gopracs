# To run this code in your terminal

# Here are the steps 
# First run
go run json.go
# for decoding
curl -s -XPOST -d'{"firstname":"danm", "lastname":"enxa","age":40}' http://localhost:8080/decode
# for encoding
curl -s http://localhost:8080/encode