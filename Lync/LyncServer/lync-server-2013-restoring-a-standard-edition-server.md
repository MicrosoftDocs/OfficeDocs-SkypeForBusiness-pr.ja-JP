---
title: Standard Edition サーバーの復元
TOCTitle: Standard Edition サーバーの復元
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202190(v=OCS.15)
ms:contentKeyID: 52056709
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Standard Edition サーバーの復元

 

_**トピックの最終更新日:** 2013-02-21_

中央管理ストアをホストしない Standard Edition サーバーに障害が発生した場合は、このセクションの手順に従います。中央管理ストアに障害が発生した場合は、「[中央管理ストアをホストするサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。


> [!TIP]
> 復元を開始する前にシステムのイメージ コピーを取得することをお勧めします。復元中に問題が発生した場合に、そのイメージをロールバック ポイントに使用できます。このイメージ コピーをオペレーティング システムと SQL Server のインストール後に作成して、証明書を復元または再登録することもできます。



## Standard Edition サーバーを復元するには

1.  問題が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーン サーバーか新規サーバーにオペレーティング システムをインストールし、証明書を復元または再登録します。
    
    > [!NOTE]
    > 組織で定めるサーバーの展開手順に従って、この手順を実行します。


2.  RTCUniversalServerAdmins グループおよび Local Administrators グループのメンバーであるユーザー アカウントから、復元するサーバーにログオンします。

3.  該当のファイル ストアを $Backup からサーバー上のファイル ストアの場所にコピーにしてファイル ストアを復元し、フォルダーを共有します。
    

    > [!IMPORTANT]
    > 復元されたファイル ストアのパスとファイル名は、ファイルを使用するコンポーネントがそのファイルにアクセスできるように、バックアップされたファイル ストアと正確に一致する必要があります。



4.  トポロジ ビルダーを実行します。
    
    1.  トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。
    
    2.  \[**既存の展開からトポロジをダウンロードする**\] をクリックし、\[**OK**\] をクリックします。
    
    3.  トポロジを選択し、\[**保存**\] をクリックします。\[**はい**\] をクリックして選択を確定します。

5.  Lync Server のインストール フォルダーまたはメディアを参照し、\\setup\\amd64\\Setup.exe にある Lync Server 展開ウィザードを開始します。Lync Server 展開ウィザードを使用して、次の操作を行います。
    
    1.  \[**手順 1: ローカル構成ストアのインストール**\] を実行して、ローカル構成ファイルをインストールします。
    
    2.  \[**手順 2: Lync Server コンポーネントのセットアップまたは削除**\] を実行して、Lync Server のサーバーの役割をインストールします。
    
    3.  \[**手順 3: 証明書の要求、インストール、または割り当て**\] を実行して、証明書を割り当てます。
    
    4.  \[**手順 4: サービスの開始**\] を実行して、サーバー上でサービスを開始します。
    
    展開ウィザードの実行の詳細については、「展開」ドキュメントで復元しているサーバーの役割を参照してください。

6.  次の操作を実行してユーザー データを復元します。
    
    1.  ExportedUserData.zip を $Backup\\ からローカル ディレクトリにコピーします。
    
    2.  ユーザー データを復元する前に Lync サービスを停止する必要があります。これを行うには、以下のように入力します。
        
            Stop-CsWindowsService
    
    3.  ユーザー データを復元するには、コマンド ラインで、次のように入力します。
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  以下のように入力し、Lync サービスを再起動します。
        
            Start-CsWindowsService

7.  この Standard Edition サーバーで応答グループを展開した場合は、応答グループの構成データを復元します。詳細については、「[応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。

8.  この Standard Edition サーバーで常設チャットを展開した場合は、常設チャット データベース (mgc.mdf) を復元します。
    
    SQL Server バックアップを使用してバックアップした常設チャット データベースは、SQL Server の復元手順を使用して復元します。
    
    Export-CsPersistentChatData コマンドレットを使用してバックアップした常設チャット データベースは、Import-CsPersistentChatData を使用して復元します。

