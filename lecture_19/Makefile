e1:
	aflat -Tsky130 -DDUT=true e1.act > e1.prs
	prspice -s "g.Vdd=1.8;g.GND=0.0" -p "exchangeP" -i "dut" -C sky130 e1.act e1_xyce.rc
	cp e1_*.dat e1

clean:
	rm -rf e1 *.prs *.sim *.vcd mem.log
