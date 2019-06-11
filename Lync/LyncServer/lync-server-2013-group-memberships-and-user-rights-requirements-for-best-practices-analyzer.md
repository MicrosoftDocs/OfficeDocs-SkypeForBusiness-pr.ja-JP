---
title: ベストプラクティスアナライザーのグループメンバーシップとユーザー権限の要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 でのベストプラクティスアナライザーのグループメンバーシップとユーザー権限の要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-21_

ベストプラクティスアナライザーを正常に実行するには、ログオンに使用するユーザーアカウントが、ローカルコンピューターの管理者グループのメンバーである必要があります。 さらに、環境をスキャンするには、ユーザーアカウントが次のグループのメンバーである必要があります。

  - **ドメイン管理者**   が、Active Directory ドメインサービスの情報を列挙し、ドメインコントローラーとグローバルカタログサーバー上の Windows Management Instrumentation (WMI) プロバイダーに電話をかけます。

  - **管理者**   は、各 Lync server 2013 内部コンピューターと各エッジサーバーで Windows Management Instrumentation (WMI) プロバイダーを呼び出し、レジストリにアクセスする必要があります。

  - **RTCUniversalReadOnlyAdmins**   フルまたは委任された読み取り専用の Lync Server 2013 管理者権限。

  - **Exchange の管理者**   は、Microsoft exchange 組織でのみ exchange の管理者のみが表示されます。

ユーザーアカウントに十分なユーザー権限がない場合は、次の2つのオプションがあります。

  - コマンドプロンプトで、 **runas**コマンドを使用して、十分なユーザー権限があるアカウントでツールを実行します。 構文は次のとおりです。
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - [ **Active Directory に接続する**] ページで、ベストプラクティスアナライザーを実行するために使用する予定のアカウントの資格情報を設定します。 [**詳細ログインオプションの表示] を**クリックします。 Active Directory ドメインサービスへの接続用に1つ、Lync Server 2013 エッジサーバーへの接続用、および Exchange サーバーへの接続用の3つのアカウントを入力できます。 これらのいずれかのアカウントを指定しない場合、ログオンに使用したユーザーアカウントとベストプラクティスアナライザーを実行するために使用されます。

</div>

<span> </span>

</div>

</div>

</div>

