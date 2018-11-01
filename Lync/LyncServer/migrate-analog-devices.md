---
title: アナログ デバイスの移行
TOCTitle: アナログ デバイスの移行
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49887095
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アナログ デバイスの移行

 

_**トピックの最終更新日:** 2012-10-16_

Lync Server では、アナログ デバイスがサポートされます。具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。 Lync Server 環境でアナログ デバイスの使用をサポートするように認定ゲートウェイを構成できます。 Lync Server 2010 から Lync Server 2013 に移行したら、アナログ デバイスに関連付けられている連絡先オブジェクトも移行する必要があります。最初に Lync Server 管理シェルを使用して Lync Server 2010 アナログ デバイスに関連付けられたすべての連絡先オブジェクトを取得し、それからこれらのオブジェクトを Lync Server 2013 プールに移動します。

## アナログ デバイスを移行するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンドラインで、次のように入力します。
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  すべての連絡先オブジェクトが Lync Server 2013 プールに移動されたことを確認します。コマンドラインで、次のように入力します。
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  すべての連絡先オブジェクトが Lync Server 2013 プールに関連付けられたことを確認します。

