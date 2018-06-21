---
title: Skype for Business Server コントロール パネル管理者の作成
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: Skype をビジネスのサーバーのアクセスを許可するには、次の操作を行います。
ms.openlocfilehash: 9f9342b02f89b31c22a50f834aa08347ba7fd798
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979030"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Skype for Business Server コントロール パネル管理者の作成
 
Skype をビジネスのサーバーのアクセスを許可するには、次の操作を行います。
  
1. Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. [**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーを右クリックし、[**プロパティ**] をクリックします。
    
3. [**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。
    
4. [メンバー] タブで [**追加**] をクリックします。[**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。CSAdministrators グループに追加するユーザー名またはグループ名を入力します。[**OK**] をクリックします。
    
5. [メンバー] タブで、選択したユーザーまたはグループが表示されていることを確認します。[**OK**] をクリックします。
    
> [!TIP]
> ビジネス サーバーのコントロール パネルの Skype は、役割ベースのアクセス制御ツールです。 CsAdministrator グループのメンバーシップは、利用可能なすべての構成機能のビジネス サーバーのコントロール パネルの [フル コントロールの Skype を使用しているユーザーを与えます。 特定の機能向けに設計されたその他の役割も使用できます。 ユーザーは、管理グループのメンバーになるために Skype ビジネス サーバーに対して有効にする必要はありません。 
  
他の役割は次のとおりです。
  
- **CsArchiving:** このグループのメンバーは、構成、およびアーカイブ サーバーの役割を管理するなど、すべてのアーカイブ機能を実行できます。
    
- **CsHelpDesk:** このグループのメンバーは、ユーザーのプロパティやポリシーを含む構成と展開を表示できます。またメンバーは、特定のトラブルシューティング タスクも実行できます。
    
- **CsLocationAdministrator:** メンバーは、Enhanced 9-1-1 (E9-1-1) の管理と関連付けられた最小限のユーザー権限を持ちます。E9-1-1 の場所およびネットワーク識別子を作成し、展開内でそれらを関連付けることができます。
    
- **CsResponseGroupAdministrator:** メンバーは、応答グループ サービスを管理および構成できます。
    
- **CsServerAdministrator:** メンバーは、管理、監視、およびビジネス サーバーの Skype を実行しているすべてのサーバーのトラブルシューティングを行うことができます。
    
- **CsUserAdministrator:** メンバーは、ユーザーの管理、有効化および無効化、ユーザーへの既存ポリシーの割り当てを実行できます。
    
- **CsViewOnlyAdministrator:** メンバーには、展開と構成のサーバーの情報を表示できます。 このメンバーシップは、ビジネス サーバー 2015 の Skype を実行しているサーバーの稼働状態を監視するにはメンバーを使用します。
    
- **CsVoiceAdministrator:** メンバーは、作成、構成、およびビジネス サーバーの Skype での音声関連の設定を管理することができます。
    
セキュリティとロール ベースのアクセス制御の整合性を確保するため、ユーザーがビジネス サーバー配置の Skype の管理を実行するどのような役割を定義するグループにユーザーを追加します。
  

