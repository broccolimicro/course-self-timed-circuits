e1:
	aflat -DDUT=true e1.act > e1.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "merge<>" -i "dut" -C sky130 e1.act e1.rc

e2:
	aflat -DDUT=true e2.act > e2.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "copy<>" -i "dut" -C sky130 e2.act e2.rc

e3:
	aflat -DDUT=true e3.act > e3.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "and<>" -i "dut" -C sky130 e3.act e3.rc

clean:
	rm -rf e1 e1.prs e2 e2.prs e3 e3.prs
