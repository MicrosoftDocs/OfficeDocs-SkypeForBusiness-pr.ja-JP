---
title: すべての Exchange UM 連絡先オブジェクトが従来のプールから削除されていることを確認する
description: すべての Exchange UM 連絡先オブジェクトが従来のプールから削除されていることを確認します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af5dea6cf746c55d8fecf074e132f721c380de1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555513"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>すべての Exchange UM 連絡先オブジェクトが従来のプールから削除されていることを確認する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-26_

**Ocsumutil**ツールまたは**Get-csexumcontact**コマンドレットを使用して、Exchange UM 連絡先オブジェクトが従来の Office Communications Server 2007 R2 プールから削除されていることを確認します。 **OCSUmUtil** は次のフォルダーにあります。

% Program Files% \\ Common Files \\ Lync Server 2013 \\ サポート \\OcsUMUtil.exe

**OCSUmUtil** は、次の条件を満たすユーザー アカウントから実行する必要があります。

  - RTCUniversalServerAdmins および RTCUniversalUserAdmins グループ (Exchange Server ユニファイド メッセージングの設定を読み取る権利が割り当てられている) に属している

  - 指定された組織単位 (OU) コンテナーに連絡先オブジェクトを作成するドメイン権限

**Get-help**コマンドレットの使用の詳細については、「Lync Server Management Shell」のドキュメントの「[取得-csexumcontact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

