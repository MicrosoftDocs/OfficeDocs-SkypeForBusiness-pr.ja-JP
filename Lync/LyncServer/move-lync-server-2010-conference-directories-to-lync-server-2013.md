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
ms.openlocfilehash: 049472022a26d7a3a6e8e78e20a20ccaa46ff5fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>会議ディレクトリの移動

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-28_

プールを使用停止にする前に、Lync Server 2010 プール内の会議ディレクトリごとに次の手順を実行する必要があります。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>会議ディレクトリを Lync Server 2013 に移動するには

1.  Lync Server 管理シェルを開きます。

2.  組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。
    
        Get-CsConferenceDirectory
    
    上記のコマンドは、組織内のすべての会議ディレクトリを返します。 そのため、廃棄されたプールに対して結果を制限する必要がある場合があります。 たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net でプールを使用停止にする場合は、次のコマンドを使用して、返されるデータをそのプールからの会議ディレクトリに制限します。
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    このコマンドは、ServiceID プロパティに FQDN pool01.contoso.net が含まれている会議ディレクトリのみを返します。

3.  会議ディレクトリを移動するには、プール内の会議ディレクトリごとに次のコマンドを実行します。
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    たとえば、会議ディレクトリ3を移動するには、次のコマンドを使用します。 Lync Server 2013 プールを TargetPool として指定します。
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    プール上のすべての会議ディレクトリを移動するには、次のようなコマンドを使用します。
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Lync 2010 プールを使用停止にするための包括的な手順については、「Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)Server 2010 のアンインストールとサーバーの役割の削除」を参照してください。

会議ディレクトリを移動すると、次のエラーが発生する場合があります。

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

通常、このエラーは、タスクを完了するために Lync Server 管理シェルで、更新された Active Directory のアクセス許可セットが必要な場合に発生します。 この問題を解決するには、管理シェルの現在のインスタンスを閉じてから、シェルの新しいインスタンスを開き、コマンドを再実行して会議ディレクトリを移動します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

