---
title: 'Lync Server 2013: コアデータと設定のバックアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4523dcaaee5931e6bf4df9dd79c09ec92636ec31
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Lync Server 2013 でのコアデータと設定のバックアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-04-23_

次の手順では、Lync Server 管理シェルコマンドレットを使用して、コアサービスの設定とデータのバックアップファイルを作成します。 このセクションで使用されているツールの詳細については、「 [Lync Server 2013 のバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)」を参照してください。ツールとアクセス許可。 アーカイブおよび監視データのバックアップの詳細については、「 [Lync Server 2013 でのアーカイブおよび監視データベースのバックアップ](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)」を参照してください。

<div>


> [!NOTE]  
> 中央管理ストアをバックアップするためのこのセクションの手順には、アーカイブと監視の設定と構成が含まれます。



</div>

ここで説明するコマンドレットは、ローカルでもリモートでも実行できます。

<div>

## <a name="to-back-up-core-data-and-settings"></a>コア データおよび設定をバックアップするには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。

2.  以下の手順で作成するバックアップを格納するため、新しい共有フォルダーを作成し、**$Backup** によって参照されているパスを新しい共有フォルダーに更新します。

3.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

4.  中央管理ストア構成ファイルをバックアップします。 コマンドラインで、次のように入力します。
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    例:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > この手順では、Lync Server のトポロジ、ポリシー、および構成設定をファイルにエクスポートします。 トポロジ データをバックアップするために他の手順は必要ありません。

    
    </div>

5.  バックアップした中央管理ストア構成ファイルを $Backup\\にコピーします。

6.  場所情報サービスのデータをバックアップします。コマンド ラインで、次のように入力します。
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    次に例を示します。
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  バックアップした場所情報サービス構成ファイルを $Backup\\にコピーします。

8.  フロントエンドプールおよびすべての Standard Edition サーバーのすべてのバックエンドデータベースについて、ユーザーデータをバックアップします。 コマンドラインで、次のように入力します。
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    例:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  バックアップしたユーザーファイルを $Backup\\にコピーします。

10. 応答グループアプリケーションが実行されているすべてのプールで、応答グループ構成をバックアップします。 次の操作を実行してください。
    
    1.  コマンドラインで、次のように入力します。
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        次に例を示します。
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. バックアップされた応答グループ構成ファイルを $Backup\\にコピーします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

