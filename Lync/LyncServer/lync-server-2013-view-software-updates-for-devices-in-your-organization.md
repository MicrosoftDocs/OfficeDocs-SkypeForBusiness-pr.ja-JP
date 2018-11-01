---
title: Lync Server 2013 でのデバイスのソフトウェア更新プログラムの表示
TOCTitle: Lync Server 2013 でのデバイスのソフトウェア更新プログラムの表示
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48273657
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのデバイスのソフトウェア更新プログラムの表示

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 では、デバイス更新 Web サービスを使用して、組織のデバイスのソフトウェア更新プログラムを表示および管理します。これらの更新プログラムは、Microsoft サポートの Web サイト ([http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0x411)) からキャビネット ファイル形式 (.cab) で入手できます。.cab ファイルのダウンロード後に、**Import-CSdeviceUpdate** コマンドレットを実行して、デバイスの更新ルールを .cab ファイルからインポートします。**Import-CSdeviceUpdate** コマンドレットの詳細については、「Lync Server 管理シェル」ドキュメントの「[Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate)」を参照してください。


> [!TIP]
> 新しい更新プログラムを組織に展開する前に、テスト デバイスで正常に動作することを検証します。



## UC デバイスのソフトウェア更新プログラムを表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Microsoft サポートの Web サイト ([http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0x411)) から, .cab ファイルを Lync Server 2013 コンピューター上の場所 (たとえば、C:\\Updates\\UCUpdates.cab) にダウンロードします。

3.  次のどちらかのコマンドレットを実行して、デバイスの更新ルールを C:\\Updates\\UCUpdates.cab ファイルからインポートします。
    
      - .cab ファイルを、更新対象のサービス (service:Redmond-websvc-2) を実行するコンピューターに置いた場合は、次のコマンドレットを実行します。
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - .cab ファイルを、更新対象のサービス (service:Redmond-websvc-3) を実行するコンピューターとは異なるコンピューターに置いた場合は、次のコマンドレットを実行します。
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

5.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイスの更新**\] をクリックします。

6.  \[**デバイスの更新**\] ページの一覧で更新プログラムをクリックし、次のいずれかを実行します。
    
      - **保留中の更新プログラムをキャンセルします。** 選択した更新プログラムを組織のデバイスに展開しないようにするには、\[**操作**\] メニューをクリックし、\[**保留中の更新の取り消し**\] をクリックします。
    
      - **更新プログラムを承認します。** 選択した更新プログラムを組織のデバイスに展開できるようにするには、\[**操作**\] メニューをクリックし、\[**承認**\] をクリックします。
    
      - **更新プログラムを復元します。** 以前承認した更新プログラムを組織のデバイスに展開できるようにするには、\[**操作**\] メニューをクリックし、\[**復元**\] をクリックします。

## 関連項目

#### その他のリソース

[Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)

