# Lab 5: PAVOL REPA

### Flip-flops

1. Listing of VHDL architecture for T-type flip-flop. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
architecture Behavioral of t_ff_rst is
begin

 p_t_ff_rst : process(clk)
    begin
        if rising_edge(clk) then  -- Synchronous process

            if (rst = '1')then
                s_q <= '0';
            else
                if (t = '0')then
                    s_q <= s_q;
                else
                    s_q <= not t;        
                end if;               
            end if;
       end if; 
       
    end process p_t_ff_rst;
    
    q <= s_q;
    q_bar <= not s_q;
    
end architecture Behavioral;
```

2. Screenshot with simulated time waveforms. Try to simulate both flip-flops in a single testbench with a maximum duration of 200 ns, including reset. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![image](https://user-images.githubusercontent.com/99768688/158580125-4c54440c-e7ca-4f7f-bb42-25e43aa70e60.png)

### Shift register

1. Image of the shift register `top` level schematic. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components and internal signals!

   ![image](https://user-images.githubusercontent.com/99768688/159161353-14fa05bf-5e81-4e8d-9147-171417dfd72b.png)
