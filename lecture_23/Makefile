e1:
	aflat -Tsky130 -DDUT=true e1.act > e1.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "exclhi_ideal<>" -i "dut" -C sky130 e1.act e1.rc

e2:
	aflat -Tsky130 -DDUT=true e2.act > e2.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "tree_arbiter<>" -i "dut" -C sky130 e2.act e2.rc

clean:
	rm -rf e1 e1.prs e2 e2.prs e3 e3.prs
