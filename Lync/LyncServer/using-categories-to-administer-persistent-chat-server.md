---
title: カテゴリを使用して常設チャット サーバーを管理する
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
ms.openlocfilehash: 52e56f776969ece55f71355ed7f184dd6dd46a91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>カテゴリを使用して常設チャット サーバーを管理する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-01_

常設チャットサーバーの展開では、多数の同時常設チャットルームをホストできます。 チャット ルームは、サーバーで一連のカテゴリに編成できます。 各チャット ルームは 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。 この編成によって、業務目的に基づいて会話を識別するのに便利な構造が作成され、管理の委任および管理の簡素化が容易になります。

<div>


> [!NOTE]  
> ユーザーに対して常設チャット (Lync client) を実行しているコンピューターでは、チャットルームの管理機能の多くは使用できますが、 <STRONG>cspersistentchatadministrator</STRONG>ロールの常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用してカテゴリを作成または管理する必要があります。



</div>

常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使ってカテゴリを作成および管理し、組織内のユーザーのチャットルームへのアクセスを設計します。

チャットルーム管理者は、1人または複数のチャットルームを管理する機能を備えています。 Lync クライアントを使用して、会議室の作成と管理を行うことができます (または、ユーザーがカスタムソリューションとワークフローを作成して呼び出すことができます)。 常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使って、会議室の作成と管理を行うこともできます。

<div>


> [!NOTE]  
> 常設チャットルームには、常設チャットカテゴリと同じ名前を付けることはできません。



</div>

チャット ルームのマネージャーは、チャット ルームのカテゴリ変更を除いて、チャット ルームのすべてのプロパティに変更を加えることができます。チャット ルームのマネージャーが行う以下の操作は制限できません。

  - チャット ルームを無効にする

  - チャット ルームの名前を変更する

  - チャット ルームの説明を変更する

  - チャット ルームの種類 (大会議室と標準) を変更する

  - チャット ルームのプライバシーを変更する (開く、閉じる、非公開にする)

  - メンバーを追加または削除する

  - チャット ルーム マネージャーを追加または削除する

  - アドインを追加または削除する

  - 招待状などの設定を変更する (カテゴリで許可されている設定に応じて)

<div>

## <a name="delegated-administration"></a>代理管理

永続的なチャットルームの作成と管理は、カテゴリを適切に使用することで非常に簡単になります。 常設チャット管理者は、各カテゴリの**Allowedmembers**と**クリエーター**を定義できます。また、カテゴリで作成されたすべてのチャットルームに適用される既定のチャットルームの設定と動作も定義できます。 常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、カテゴリの作成と管理を行います。

カテゴリの Creators として特定されるユーザー、組織単位 (OU)、ユーザー グループは、そのカテゴリのチャット ルームの作成を許可されている個人およびグループです。カテゴリを作成した後、これらの個人およびグループは、**AllowedMembers** リストからユーザー、OU、ユーザー グループをチャット ルームの管理と参加が可能なマネージャーおよびメンバーとして選択できます。

カテゴリで作成されたチャットルームは、カテゴリによって適用されるポリシーと設定 (ルームのメンバーシップに含まれるユーザー、ルームを管理できるユーザー、ファイルのアップロードが許可されているかどうか、招待を送信するかどうかなど) に従っています。

</div>

</div>

<span> </span>

</div>

</div>

</div>

