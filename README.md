# hello-world
my first repository
import sys

file = sys.argv[1]

# open file and read by lines
# make a list of block domain name
def file2list (block_list):
	name_list = []
	
	with open(block_list) as f:
		name_list = f.readlines()
		name_list = [name.strip() for name in name_list]
		
	return name_list

# launch dns queries
def nslookup (dnames):
	import socket
	ip_list =[]
	
	for dname in dnames:
#		try:
			ip = socket.gethostbyname(dname)
			ip_list.append(ip)
#		except QueryError:
#			print("Error: DNSquery is failed")
		
	return ip_list

# print the outcome
out_list = nslookup(file2list(file))
for i in out_list:
	print(i)
