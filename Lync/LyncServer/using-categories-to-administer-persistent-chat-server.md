---
title: カテゴリを使用して常設チャットサーバーを管理する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2aa30e39594bfa0a294b4ad0d5755cdcb60c090
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>カテゴリを使用して常設チャットサーバーを管理する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-01_

常設チャットサーバーの展開では、複数の常設チャットルームをホストできます。 チャット ルームはサーバー上で一連のカテゴリに分類できます。 チャット ルームはそれぞれ 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。 このように体系化することで、会話を業務目的に基づいて識別するのに役立つ構造が作成され、管理の委任と簡素化が促進されます。

<div>


> [!NOTE]  
> チャットルームの管理機能の多くは、ユーザーの常設チャット (Lync client) を実行しているコンピューターで利用できますが、常設チャット管理者 ( <STRONG>cspersistentchatadministrator</STRONG>の役割) では、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用してカテゴリを作成または管理する必要があります。



</div>

常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用してカテゴリを作成および管理し、組織内のユーザーのためのチャットルームへのアクセスを設計します。

1つまたは複数のチャットルームを管理できる常設チャットルームマネージャーは、Lync クライアントを使用してルーム管理 Web アプリケーションを起動し、会議室を作成および管理します (または、お客様はカスタムソリューションやワークフローを作成して呼び出すことができます)。 常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、会議室を作成および管理することもできます。

<div>


> [!NOTE]  
> 常設チャットルームには、常設チャットのカテゴリと同じ名前を付けることはできません。



</div>

チャット ルームのマネージャーは、ルームのカテゴリを変更することを除いて、チャット ルームのすべてのプロパティを変更できます。チャット ルームのマネージャーによる次の操作を制限することはできません。

  - チャット ルームを無効にする

  - チャット ルームの名前を変更する

  - チャット ルームの説明を変更する

  - チャット ルームの種類 (大会議室と標準) を変更する

  - ルームのプライバシーを変更する (オープンかクローズか秘密か)

  - メンバーを追加または削除する

  - チャット ルーム マネージャーを追加または削除する

  - アドインを追加または削除する

  - 招待などの設定を変更する (カテゴリで許可されている操作に応じて)

<div>

## <a name="delegated-administration"></a>委任された管理

カテゴリを適切に使用すると、常設チャットルームの作成と管理が非常に簡単になります。 常設チャット管理者は、各カテゴリに**Allowedmembers**と**クリエーター**を定義でき、カテゴリに作成されたすべてのチャットルームに適用される既定のチャットルームの設定と動作を定義することもできます。 常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、カテゴリを作成および管理します。

カテゴリの作成者として識別されるユーザー、組織単位 (Ou)、ユーザーグループは、カテゴリ内のルームの作成を許可されている個人およびグループのみです。 カテゴリが作成されると、カテゴリの**Allowedmembers**リストからユーザー、ou、およびユーザーグループを選択して、チャットルームマネージャーと、ルームに参加するためのメンバーを管理することができます。

カテゴリに作成されたチャットルームは、カテゴリによって適用されるポリシーと設定 (ルームのメンバーシップに含まれるユーザー、ルームを管理できるユーザー、ファイルのアップロードが許可されているかどうか、招待が送信されるかどうかなど) に従います。

</div>

</div>

<span> </span>

</div>

</div>

</div>

