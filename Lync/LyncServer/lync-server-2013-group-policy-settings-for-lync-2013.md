---
title: 'Lync Server 2013: Lync 2013 のグループポリシー設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937869dffc3dfecc994f3c9ce819e1a644c88abe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 のグループポリシー設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

以前のバージョンの Lync および Office Communicator では、スタンドアロンの Communicator 管理用テンプレートを使用してクライアントグループポリシー設定を構成できました。 Lync 2013 では、新しい管理用テンプレートファイル (admx および adml ファイル) が Office グループポリシー管理用テンプレートと共に含まれています。 Lync 2013 ファイルと adml ファイルを使用すると、テンプレートをダウンロードして、すべての Office プログラムおよび言語パックのグループポリシー設定を一元管理できます。 詳細については、Office 2013 のドキュメントの「Office 2013 管理用テンプレートファイル (ADMX, ADML <https://go.microsoft.com/fwlink/p/?linkid=267516>)」を参照してください。

<div>

## <a name="client-bootstrapping-policies"></a>クライアント ブートストラップ ポリシー

ユーザーが初めてサーバーにサインインする前に、幾つかのクライアント ブートストラップ ポリシーを構成する必要があります。 これらのポリシーは、クライアントがサインインする前に有効になり、サーバーからインバンド プロビジョニング設定を受け取るようになるため、グループ ポリシーを使って構成できます。 詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのクライアントブートストラップポリシーの構成](lync-server-2013-configuring-client-bootstrapping-policies.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

