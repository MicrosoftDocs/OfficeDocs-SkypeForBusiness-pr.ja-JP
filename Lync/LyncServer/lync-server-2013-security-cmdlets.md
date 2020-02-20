---
title: 'Lync Server 2013: セキュリティコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b1461c006a68dff3241d859f5daf91db09e4be0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-cmdlets-in-lync-server-2013"></a>Lync Server 2013 のセキュリティコマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

Microsoft Lync Server 2013 に含まれているセキュリティコマンドレットは、主に、認証、ユーザー権限、アクセス許可を管理するために使用されます。 認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。 さらに、いくつかのコマンドレットを使用して、新しい役割ベースのアクセス制御 (RBAC) 機能を使用して、Lync Server の管理制御を委任することができます。

<div>

## <a name="security-cmdlets"></a>セキュリティのコマンドレット

セキュリティ設定に適用される多くの管理タスクは、Lync Server コントロールパネルから実行できます。 1つの重要な例外は、ユーザーアクセス許可のコマンドレットです。 ただし、すべてのセキュリティ管理タスクは、Lync Server 管理シェルまたはスクリプト内からコマンドレットを使用して実行できます。スクリプトを使用すると、特定のタスクを自動化できます。 以下に、セキュリティ設定の管理に直接関連するコマンドレットの一覧を示します。

**[Lync Server 2013 の証明書と認証のコマンドレット](lync-server-2013-certificate-and-authentication-cmdlets.md)**

  - <span></span>  
    [-CsCertificate の取得](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - <span></span>  
    [インポート-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - <span></span>  
    [削除-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - <span></span>  
    [要求-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - <span></span>  
    [設定-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-Cs/Test](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Revoke-csclientcertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - <span></span>  
    [Revoke-csclientcertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [ロック-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - <span></span>  
    [-CsClientPin の設定](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - <span></span>  
    [ロック解除-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsClientPinInfo を取得する](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-Csker' Osaccount '](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-Csker' Osaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsProxyConfiguration の取得](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - <span></span>  
    [新しい-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - <span></span>  
    [-CsProxyConfiguration を削除する](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - <span></span>  
    [設定-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipdomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - <span></span>  
    [New-cssipdomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - <span></span>  
    [New-cssipdomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - <span></span>  
    [New-cssipdomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

**[Lync Server 2013 のユーザー権限とアクセス許可のコマンドレット](lync-server-2013-user-rights-and-permissions-cmdlets.md)**

  - <span></span>  
    [-CsAdminRole の取得](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - <span></span>  
    [新しい-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - <span></span>  
    [-CsAdminRole の削除](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - <span></span>  
    [設定-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - <span></span>  
    [-CsAdminRole の更新](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsAdminRoleAssignment の取得](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [付与-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - <span></span>  
    [Revoke-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - <span></span>  
    [テスト-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - <span></span>  
    [失効-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - <span></span>  
    [テスト-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

**[Lync Server 2013 の相互運用性のコマンドレット](lync-server-2013-interoperability-cmdlets.md)**

  - [取得-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

<!-- end list -->

  - [取得-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [新しい-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

<!-- end list -->

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server PowerShell ブログ](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

