---
title: バックエンドサーバーまたは Standard Edition サーバーをアップグレードまたは更新する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213a945d27c2c5d0ee2135fd0d96bbe1c29c1971
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42015360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013 でのバックエンドサーバーまたは Standard Edition サーバーのアップグレードまたは更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このトピックでは、Enterprise Edition バックエンドサーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。

アップグレード中のバックエンドサーバーが少なくとも30分間ダウンすると、ユーザーは復元モードになることがあります。 アップグレードが完了し、バックエンドサーバーがプール内のフロントエンドサーバーに再度接続されると、ユーザーはすべての機能に戻ります。 アップグレードの時間が30分未満の場合、ユーザーに影響はありません。

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>バックエンドサーバーまたは Standard Edition サーバーを更新するには

1.  CsAdministrator の役割のメンバーとして、アップグレードするサーバーにログオンします。

2.  更新プログラムをダウンロードして、ローカルハードディスクに抽出します。

3.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

4.  Lync Server サービスを停止します。 コマンドラインで、次のように入力します。
    
        Stop-CsWindowsService

5.  World Wide Web サービスを停止します。 コマンドラインで、次のように入力します。
    
        net stop w3svc

6.  すべての Lync Server 管理シェルウィンドウを閉じます。

7.  更新プログラムをインストールします。

8.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

9.  Lync Server サービスを再度停止して、グローバルアセンブリキャッシュ (GAC) – d アセンブリをキャッチします。 コマンドラインで、次のように入力します。
    
        Stop-CsWindowsService

10. World Wide Web サービスを再起動します。 コマンドラインで、次のように入力します。
    
        net start w3svc

11. 以下のいずれかの処理を行って、LyncServerUpdateInstaller.exe による SQL Server データベースへの変更を適用します。
    
      - これが Enterprise Edition バックエンドサーバーで、アーカイブデータベースや監視データベースなど、このサーバーに併置されたデータベースがない場合は、コマンドラインで次のように入力します。
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - これが Enterprise Edition バックエンドサーバーで、このサーバーに併置されたデータベースがある場合は、コマンドラインで次のように入力します。
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Standard Edition サーバーの場合は、コマンドラインで次のように入力します。
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

