---
title: 'Lync Server 2013: コアデータと設定のバックアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1737dac3369361b0937e6b870839e11e5706e41a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Lync Server 2013 でのコアデータと設定のバックアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-04-23_

次の手順では、Lync Server Management Shell コマンドレットを使用して、コアサービスの設定とデータのバックアップファイルを作成します。 このセクションで使用されるツールの詳細については、「 [Lync Server 2013 のバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)」を参照してください。ツールと権限。 アーカイブと監視データのバックアップの詳細については、「 [Lync Server 2013 でのアーカイブと監視データベースのバックアップ](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)」を参照してください。

<div>


> [!NOTE]  
> このセクションの中央管理ストアをバックアップする手順には、アーカイブと監視の設定と構成が含まれます。



</div>

このセクションで説明されているコマンドレットは、ローカルまたはリモートで実行できます。

<div>

## <a name="to-back-up-core-data-and-settings"></a>コアデータと設定をバックアップするには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、社内展開の任意のコンピューターにログオンします。

2.  次の手順で作成したバックアップを保存するには、新しい共有フォルダーを作成し、 **$Backup**によって参照されるパスを新しい共有フォルダーに更新します。

3.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

4.  一元管理ストア構成ファイルをバックアップします。 コマンドラインで、次のように入力します。
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    次に例を示します。
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > この手順では、Lync サーバーのトポロジ、ポリシー、構成の設定をファイルにエクスポートします。 トポロジデータをバックアップするために、他の手順は必要ありません。

    
    </div>

5.  バックアップされた全体管理ストア構成ファイルを $Backup\\にコピーします。

6.  位置情報サービスのデータをバックアップします。 コマンドラインで、次のように入力します。
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    次に例を示します。
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  バックアップされた場所情報サービス構成ファイルを $Backup\\にコピーします。

8.  フロントエンドプールおよびすべての Standard Edition サーバーの各バックエンドデータベースで、ユーザーデータをバックアップします。 コマンドラインで、次のように入力します。
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    次に例を示します。
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  バックアップされたユーザーファイルを $Backup\\にコピーします。

10. 応答グループアプリケーションを実行するすべてのプールで、応答グループの構成をバックアップします。 次の手順を実行します。
    
    1.  コマンドラインで、次のように入力します。
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        例:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. バックアップされた応答グループ構成ファイルを $Backup\\にコピーします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

