e1:
	aflat -DDUT=true e1.act > e1.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "wchb<>" -i "dut" -C sky130 e1.act e1.rc

clean:
	rm -rf e1 e1.prs
