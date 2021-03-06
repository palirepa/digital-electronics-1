# Lab 7: PAVOL REPA

### Display driver

1. Listing of VHDL code of the completed process `p_mux`. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
    --------------------------------------------------------
    -- p_mux:
    -- A sequential process that implements a multiplexer for
    -- selecting data for a single digit, a decimal point 
    -- signal, and switches the common anodes of each display.
    --------------------------------------------------------
   p_mux : process(clk)
    begin
        if rising_edge(clk) then
            if (reset = '1') then
                s_hex <= data0_i;
                dp_o  <= dp_i(0);
                dig_o <= "1110";
            else
                case s_cnt is
                    when "11" =>
                        s_hex <= data3_i;
                        dp_o  <= dp_i(3);
                        dig_o <= "0111";

                    when "10" =>
                        -- DEFINE ALL OUTPUTS FOR "10" HERE
                        s_hex <= data2_i;
                        dp_o  <= dp_i(2);
                        dig_o <= "1011";
                    when "01" =>
                        -- DEFINE ALL OUTPUTS FOR "01" HERE
                        s_hex <= data1_i;
                        dp_o  <= dp_i(1);
                        dig_o <= "1101";
                    when others =>
                        -- DEFINE ALL OUTPUTS FOR "00" HERE
                        s_hex <= data0_i;
                        dp_o  <= dp_i(0);
                        dig_o <= "1110";
                end case;
            end if;
        end if;
    end process p_mux;
```

2. Screenshot with simulated time waveforms. Test reset as well. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![image](https://user-images.githubusercontent.com/99768688/160815770-ea69472a-df18-448e-8580-1e2f53925f17.png)

### Eight-digit driver

1. Image of the 8-digit driver's block schematic. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components, and internal signals!

   ![image](https://user-images.githubusercontent.com/99768688/161388022-fd33328a-ecc2-41f2-8ca2-1b350f16b84f.png)
