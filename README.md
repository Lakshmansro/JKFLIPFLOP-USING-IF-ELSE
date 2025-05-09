JKFLIPFLOP-USING-IF-ELSE
AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

image

This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

image

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

image

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

image

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

Procedure

Go to quartus software.
Set new environment.
Type the code to implement SR flipflop using verilog and validating their functionality using their functional tables.
Run the program.
Give inputs in the waveform table.
Run the program.
PROGRAM

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
Developed by: GAUTHAM KRISHNA S
RegisterNumber: 212223240036
*/
module JK(q, qb,j,k,clock,reset);
    input j,k,clock,reset;
    output reg q, qb;
	 
always @ (posedge (clock))

    begin 
        if (!reset)
            begin
               q <= q;
               qb <=qb;
            end   
        
else
	begin
		if(j==0&&k==0)
			begin
			q<=q;
			qb<=qb;
			end
		else if(j!=k)
			begin
			q<=j;
			qb<=k;
			end
		else if(j==1&&k==1)
			begin
			q<=~q;
			qb<=~qb;
			end
	end
end
            
endmodule
RTL LOGIC FOR FLIPFLOPS

image

TIMING DIGRAMS FOR FLIP FLOPS

image

RESULT:

Implementation of JK flipflop using verilog and validating their functionality using their functional tables is executed and the output is verified successfully.
