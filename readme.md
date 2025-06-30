
<block type="trade">
  <variables>
    <variable type="int" name="trade_count" value="0"/>
  </variables>
  <on_tick>
    <if condition="3 bullish or bearish candles">
      <do>
        <if condition="trade_count < 5">
          <do>
            <trade type="CALL or PUT" stake="5%" duration="1" duration_unit="minute"/>
            <wait seconds="60"/>
            <set name="trade_count" value="trade_count + 1"/>
          </do>
        </if>
      </do>
    </if>
  </on_tick>
</block>