---
title: 'Lync Server 2013: 既定のピクチャオプションの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3b5007a1d850e1a271c507290c48a2c8d345c7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a>Lync Server 2013 での既定の画像のオプションの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-22_

既定では、ユーザーの画像が自動的に表示されます。 ユーザーが画像を非表示にする場合は、Lync クライアントで [**自分の画像を表示**しない] オプションを選択できます。 ただし、この設定は他の Office アプリケーションでは無視されます。

ユーザーによって無効にされていても画像が表示される可能性がある場合は、Lync 画像の表示設定をグローバルに、またはサイトまたはサービス用に変更して、ユーザーの画像が既定で表示されないようにすることができます。 次の Lync Server 管理シェルコマンドレットを使用して、クライアントで [**自分の画像を表示**する] オプションを明示的に選択しない限り、ユーザーの画像が表示されないようにします。

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csprivacyconfiguration 戻し](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

