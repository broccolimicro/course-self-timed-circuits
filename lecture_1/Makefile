e1:
	aflat e1.act > e1.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "inverter<>" -i "dut" -C sky130 e1.act e1.rc

e2:
	aflat e2.act > e2.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "nand_gate<>" -i "dut" -C sky130 e2.act e2.rc

clean:
	rm -rf e1 e1.prs e2 e2.prs
