---
title: ベストプラクティスアナライザーのグループメンバーシップとユーザー権限の要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2245cbbe32e8751948f32dc83dae7ca58f92091f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 のベストプラクティスアナライザーのグループメンバーシップとユーザー権限の要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-21_

ベスト プラクティス アナライザーを正常に実行するには、ログオンで使用したユーザー アカウントがローカル コンピューターの Administrators グループのメンバーである必要があります。また、環境をスキャンするには、ユーザー アカウントが次のグループのメンバーである必要があります。

  - **ドメイン管理者**   は、Active Directory ドメインサービスの情報を列挙し、ドメインコントローラーおよびグローバルカタログサーバーの Windows Management Instrumentation (WMI) プロバイダーを呼び出すことができます。

  - **管理者**   は、各 Lync server 2013 内部コンピューターと各エッジサーバーで、Windows Management Instrumentation (WMI) プロバイダを呼び出し、レジストリにアクセスする必要があります。

  - **RTCUniversalReadOnlyAdmins**   Full または委任されたすべての読み取り専用 Lync Server 2013 の管理者権限。

  - **Exchange view only 管理者**   完全または委任された Microsoft exchange 組織の管理者のみ。

ユーザー アカウントで十分なユーザー権限がない場合、2 つのオプションがあります。

  - コマンド プロンプトで、**runas** コマンドを使って十分なユーザー権限があるアカウントからツールを実行します。 構文は次のとおりです。
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - [ **Active Directory への接続**] ページで、ベストプラクティスアナライザーを実行するために使用する予定のアカウントの資格情報を設定します。 [**詳細なログインオプションの表示] を**クリックします。 3つのアカウントを入力できます。1つは Active Directory ドメインサービスへの接続用、もう1つは Lync Server 2013 エッジサーバーへの接続用、もう1つは Exchange サーバーへの接続用です。 これらのアカウントのいずれも指定しない場合は、ログオンしてベストプラクティスアナライザーを実行するために使用したユーザーアカウントが使用されます。

</div>

<span> </span>

</div>

</div>

</div>

