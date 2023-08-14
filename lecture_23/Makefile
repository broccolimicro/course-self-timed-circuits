e1:
	aflat -Tsky130 -DDUT=true e1.act > e1.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "maybe_execute<>" -i "dut" -C sky130 e1.act e1_xyce.rc

e2:
	aflat -Tsky130 -DDUT=true e2.act > e2.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "bundling_merge<>" -i "dut" -C sky130 e2.act e2_xyce.rc

e3:
	aflat -Tsky130 -DDUT=true e3.act > e3.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "greedy_arbiter<>" -i "dut" -C sky130 e3.act e3_xyce.rc

clean:
	rm -rf e1 e1.prs e2 e2.prs e3 e3.prs mem.log
