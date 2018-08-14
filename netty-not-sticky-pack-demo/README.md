# netty-not-sticky-pack-demo

## ���tcp�������ݣ�ճ������  
�Ƚ������Ľ�����������¼��֣�  
1����Ϣ���������Ĵ�С�̶����ȣ�����ÿ�����ĵĳ��ȹ̶�Ϊ200�ֽڣ����������λ���ո�  
2����β�������ָ���������ÿ�����Ľ�������ӻس����з�������FTPЭ�飩����ָ�������ַ���Ϊ���ķָ��������շ�ͨ������ָ����зֱ������֣�  
3������Ϣ��Ϊ��Ϣͷ����Ϣ�壬��Ϣͷ�а�����ʾ��Ϣ���ܳ��ȣ�������Ϣ�峤�ȣ����ֶΣ�  
4���Զ�������ӵ�Ӧ�ò�Э�顣  

## Nettyճ���Ͳ���������
Netty�ṩ�˶�������������Խ��зְ��Ĳ������ֱ��ǣ�  
LineBasedFrameDecoder  
DelimiterBasedFrameDecoder���������ָ����������ְ���  
FixedLengthFrameDecoder��ʹ�ö����ı������ְ���  
LengthFieldBasedFrameDecoder  

## LengthFieldBasedFrameDecoder
��ʵ��ʹ��LengthFieldBasedFrameDecoder����TCP�ײ�Ĳ����ճ������  
ʹ�ö�����д���  
LengthFieldBasedFrameDecoder�Ĺ��캯����  
````java
public class LengthFieldBasedFrameDecoder extends ByteToMessageDecoder {
    //...
  public LengthFieldBasedFrameDecoder(ByteOrder byteOrder, 
                                    int maxFrameLength, 
                                    int lengthFieldOffset, 
                                    int lengthFieldLength, 
                                    int lengthAdjustment, 
                                    int initialBytesToStrip, 
                                    boolean failFast) {
   }
   //...
}
````
byteOrder����ʾ�ֽ�����ʾ�������Ǵ�˻���С�ˣ���ΪNettyҪ��ȡLength�ֶε�ֵ�����Դ��С��Ҫ���úã�Ĭ��Netty�Ǵ����ByteOrder.BIG_ENDIAN��  
maxFrameLength����ʾ���ǰ�����󳤶ȣ�����������󳤶�netty���ᱨ��  
lengthFieldOffset��ָ���ǳ�����Length����ƫ��������ʾ����ָ�����ȸ��ֽ�֮��Ĳ��ǳ�����Ҳ����lengthǰ����ֽڣ�Ҳ����ͷ����Ϣ��  
lengthFieldLength����¼��֡���ݳ��ȵ��ֶα���ĳ��ȣ�  
lengthAdjustment�����ֶμӳ����ֶε�������֡�ĳ��ȣ����峤�ȵ����Ĵ�С�����������ֵ��ʾ�ĳ��ȼ����������ֵ��ʾ�ľ��Ǵ�header�İ���  
initialBytesToStrip��������֡���������ֽ�������ʾ��ȡ��һ�����������ݰ�֮�󣬺���ǰ���ָ����λ�����ֽڣ�Ӧ�ý������õ��ľ��ǲ�������������ݰ���  
failFast�����Ϊtrue�����ʾ��ȡ��������TA��ֵ�ĳ���maxFrameLength�����׳�һ�� TooLongFrameException����Ϊfalse��ʾֻ�е�������ȡ�곤�����ֵ��ʾ���ֽ�֮�󣬲Ż��׳� TooLongFrameException��Ĭ�����������Ϊtrue�����鲻Ҫ�޸ģ�������ܻ�����ڴ������  







