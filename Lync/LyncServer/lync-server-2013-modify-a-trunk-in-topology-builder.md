---
title: Lync Server 2013 でのトポロジ ビルダーによるトランクの変更
TOCTitle: Lync Server 2013 でのトポロジ ビルダーによるトランクの変更
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49887022
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのトポロジ ビルダーによるトランクの変更

 

_**トピックの最終更新日:** 2012-09-21_

トランクの代替メディア IP アドレスおよび代替バイパス ID を変更するには、以下の手順に従います。

## トランクの代替メディア IP アドレスを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  Set-CsPstnGateway コマンドレットを実行し、Lync Server 管理シェルで AlternateBypassId フィールドを変更します。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

## トランクの代替バイパス ID を変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  Set-CsPstnGateway コマンドレットを実行し、Lync Server 管理シェルで AlternateBypassId フィールドを変更します。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

