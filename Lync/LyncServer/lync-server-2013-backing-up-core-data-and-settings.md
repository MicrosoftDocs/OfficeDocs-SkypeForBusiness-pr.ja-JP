---
title: コア データと設定のバックアップ
TOCTitle: コア データと設定のバックアップ
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202170(v=OCS.15)
ms:contentKeyID: 52056563
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# コア データと設定のバックアップ

 

_**トピックの最終更新日:** 2014-04-23_

以下の手順では、Lync Server 管理シェルのコマンドレットを使用して、コア サービスの設定とデータのバックアップ ファイルを作成します。ここで使用するツールの詳細については、ツールがある場所も含めて、「[バックアップと復元の要件: ツールとアクセス許可](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)」を参照してください。アーカイブ データおよび監視データのバックアップの詳細については、「[アーカイブ データベースと監視データベースのバックアップ](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)」を参照してください。

> [!NOTE]
> ここで説明する中央管理ストアをバックアップするための手順には、アーカイブおよび監視の設定と構成が含まれます。


ここで説明するコマンドレットは、ローカルでもリモートでも実行できます。

## コア データおよび設定をバックアップするには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。

2.  以下の手順で作成するバックアップを格納するため、新しい共有フォルダーを作成し、**$Backup** によって参照されているパスを新しい共有フォルダーに更新します。

3.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

4.  中央管理ストアの構成ファイルをバックアップします。コマンド ラインで、次のように入力します。
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    次に例を示します。
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    > [!NOTE]
    > この手順では、Lync Server のトポロジ、ポリシー、および構成設定をファイルにエクスポートします。トポロジ データをバックアップするために他の手順は必要ありません。


5.  バックアップした中央管理ストアの構成ファイルを $Backup\\ にコピーします。

6.  場所情報サービスのデータをバックアップします。コマンド ラインで、次のように入力します。
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    次に例を示します。
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  バックアップした場所情報サービスの構成ファイルを $Backup\\ にコピーします。

8.  フロント エンド プールのすべてのバックエンド データベースおよびすべての Standard Edition サーバーで、ユーザー データをバックアップします。コマンド ラインで、次のように入力します。
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    次に例を示します。
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  バックアップしたユーザー ファイルを $Backup\\ にコピーします。

10. 応答グループ アプリケーションを実行するすべてのプールで、応答グループの構成をバックアップします。次の手順を実行します。
    
    1.  コマンドラインで、次のように入力します。
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        次に例を示します。
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. バックアップした応答グループの構成ファイルを $Backup\\ にコピーします。

