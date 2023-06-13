# Vending Machine
This project involved implementing the mechanism of a vending machine using verilog.
It is a sequential circuit program implemneted using Vivado-Xylinx on Basys 3 artix-7 FPGA trainer board 

The vending machines usually work when some money (usually coins or paper money) is put in
a slot. Then a button needs to be pushed, or a lever pulled. If there is enough money in
the machine, the selected item will be dropped onto a tray, where it can be taken out by
the person making the purchase. Older vending machines were mechanical, but most
new ones are electronic. The work flow is as follow 

I. When the user puts in money, money counter tells the control unit, the amount of
money inserted in the Vending Machine.
II. When the user presses the button to purchase the item that he wants, the control
unit turns on the motor and dispenses the product if correct amount is inserted.
III. If there is any change, machine will return it to the user.
IV. The machine will demand for servicing when the products are not available
inside the machine

#### Design methodology
- The state diagram mainly consists of four states (User Selection, Waiting for the
money insertion, product delivery and servicing (when product_not_available=’1’)).
Initially when the reset button is pressed, the machine will be ready for the users to
select the product. This state is the initial state of the design. After this the user will
select the product to be dispensed. This state can be one of the select1, select2,
select3 and select 4. The machine can accept only two types of notes i.e. rupees 10/-
and 20/-. Let us suppose that the user selects sel1 input. The machine will first check
whether the products are available in the machine or not. After this the control unit
will move to the waiting state, where it will wait for the money to be inserted. Then
if rupees 10/- note is inserted then the machine will go to state_1 and wait until the
desired money is inserted. And if rupees 20/- note is inserted the machine will move
to state_2 and then wait until 30/- rupees are inserted to the machine. When the
desired amount is inserted, the machine will go to the snacks state and snacks will be
delivered to the product output. If products are not available in the machine, then the
control unit will demand servicing and after service the machine will get reset.

![image](https://github.com/Dhruva-Sahani/VendingMachineProj/assets/92433769/01df826c-8372-4f24-a98b-088968e907f2)
