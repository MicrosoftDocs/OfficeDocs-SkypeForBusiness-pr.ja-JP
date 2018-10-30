---
title: コール パーク保留音のカスタマイズ
TOCTitle: コール パーク保留音のカスタマイズ
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49886925
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# コール パーク保留音のカスタマイズ

 

_**トピックの最終更新日:** 2012-09-10_

Lync Server 2013 に含まれる既定の音楽ファイルではなく、自分の音楽ファイルを保留音に使用するように指定できます。保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。

> [!NOTE]
> 保留音をカスタマイズして、同じ音楽を複数のサイトで使用したい場合は、コール パーク アプリケーションを実行するサイトごとに音楽ファイルを構成する必要があります。


## 音楽ファイルをカスタマイズするには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    

    > [!TIP]
    > サービスを識別するには、<STRONG>Get-CsService</STRONG> コマンドレットを使用します。詳細については、「<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService">Get-CsService</A>」を参照してください。

    
    次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。次に音声ファイルをコール パークの保留音ファイルとして割り当てます。詳細については、「[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)」を参照してください。
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

## 関連項目

#### その他のリソース

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)

