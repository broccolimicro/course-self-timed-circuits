e1:
	aflat -DDUT=true e1.act > e1.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "reg<>" -i "dut" -C sky130 e1.act e1.rc

clean:
	rm -rf e1 e1.prs e2 e2.prs e3 e3.prs
