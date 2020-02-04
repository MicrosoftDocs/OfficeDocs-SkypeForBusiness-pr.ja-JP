---
title: Lync Server 2010 会議ディレクトリを Lync Server 2013 に移動する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9bd597665f389c814fbdc8fe1745587fd3d1b3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>会議ディレクトリを移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-28_

プールを解除する前に、Lync Server 2010 プールの各会議ディレクトリに対して、次の手順を実行する必要があります。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>会議ディレクトリを Lync Server 2013 に移動するには

1.  Lync Server 管理シェルを開きます。

2.  組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。
    
        Get-CsConferenceDirectory
    
    上のコマンドは、組織内のすべての会議ディレクトリを返します。 そのため、廃棄されたプールに結果を制限することができます。 たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net を使用してプールを廃止する場合は、このコマンドを使用して、返されるデータをそのプールの会議ディレクトリに制限します。
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    このコマンドは、ServiceID プロパティに FQDN pool01.contoso.net が含まれている会議ディレクトリだけを返します。

3.  会議ディレクトリを移動するには、プール内の各会議ディレクトリに対して、次のコマンドを実行します。
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    たとえば、会議ディレクトリ3を移動するには、次のコマンドを使用します。 Lync Server 2013 プールを TargetPool として指定します。
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    すべての会議ディレクトリをプールに移動する場合は、次のようなコマンドを使用します。
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Lync 2010 プールの使用を停止するための包括的な手順については、「Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)Server 2010 をアンインストールし、サーバーの役割を削除する」を参照してください。

会議ディレクトリを移動すると、次のようなエラーが発生する場合があります。

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

このエラーは通常、Lync Server 管理シェルでタスクを完了するために、更新された Active Directory のアクセス許可セットが必要な場合に発生します。 この問題を解決するには、管理シェルの現在のインスタンスを閉じてから、シェルの新しいインスタンスを開き、コマンドを再実行して会議ディレクトリを移動します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

