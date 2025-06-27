---
title: "程控电源的程序控制"
categories: [技术,可编程仪器]
pin: false
---


### Rigol DP811A程控电源程控测试

```

if __name__ == '__main__' :

    import pyvisa;
    rm = pyvisa.ResourceManager()
   # reslist = rm.list_resources();
    inst = rm.open_resource('USB0::0x1AB1::0x099C::DSG8A170200001::INSTR')  # 设备地址，设备可查询
    inst.write("*IDN?")
    print(inst.read())
    inst.write(":SOURce:FREQuency 1GHz")#设置频率
    inst.write(":SOURce:LEVel -10dBm")#设置幅度
    inst.write(":OUTPut:STATe ON")#打开RF开关
    rm.close()

```

### Rigol DP811A 程控电源电压电流控制实例

```
#程控电源的控制

import pyvisa
rm = pyvisa.ResourceManager()
power_supply = rm.open_resource("TCPIP0::10.10.157.221::INSTR")  # 替换为实际设备地址

# 设置输出电压和电流
power_supply.write(":APPL CH1,2,1")  # 设为5V,1A
# power_supply.write("CURR 2.0")  # 电流限制1A
power_supply.write("OUTP ON")   # 开启输出

# 读取状态
status = power_supply.query("OUTP?")
print("Output Status:", status)

# print(power_supply)

```
