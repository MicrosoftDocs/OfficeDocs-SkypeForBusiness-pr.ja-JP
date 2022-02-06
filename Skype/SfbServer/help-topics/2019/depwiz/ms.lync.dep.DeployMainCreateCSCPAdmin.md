---
title: Skype for Business Server コントロール パネル管理者の作成
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: 'NOINDEX, NOFOLLOW'
description: ユーザーにアクセス権を付与Skype for Business Server、次の操作を行います。
---

# <a name="create-skype-for-business-server-control-panel-administrators"></a>Skype for Business Server コントロール パネル管理者の作成
 
ユーザーにアクセス権を付与Skype for Business Server、次の操作を行います。
  
1. Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. [**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーを右クリックし、[**プロパティ**] をクリックします。
    
3. [**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。
    
4. [メンバー] タブで [**追加**] をクリックします。[**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。CSAdministrators グループに追加するユーザー名またはグループ名を入力します。[**OK**] をクリックします。
    
5. [メンバー] タブで、選択したユーザーまたはグループが表示されていることを確認します。[**OK**] をクリックします。
    
> [!TIP]
> [Skype for Business Serverコントロール パネル] は、役割ベースのアクセス制御ツールです。 CsAdministrator グループのメンバーシップは、使用可能なすべての構成機能に対して Skype for Business Server コントロール パネルフル コントロールを使用しているユーザーに提供します。 特定の機能向けに設計されたその他の役割も使用できます。 管理グループのメンバーを作成するには、Skype for Business Serverを有効にする必要があります。 
  
その他の役割は次のとおりです。
  
- **CsArchiving:** このグループのメンバーは、アーカイブ サーバーの役割の構成と管理など、すべてのアーカイブ機能を実行できます。
    
- **CsHelpDesk:** このグループのメンバーは、ユーザーのプロパティやポリシーを含む構成と展開を表示できます。またメンバーは、特定のトラブルシューティング タスクも実行できます。
    
- **CsLocationAdministrator:** メンバーは、Enhanced 9-1-1 (E9-1-1) の管理と関連付けられた最小限のユーザー権限を持ちます。E9-1-1 の場所およびネットワーク識別子を作成し、展開内でそれらを関連付けることができます。
    
- **CsResponseGroupAdministrator:** メンバーは、応答グループ サービスを管理および構成できます。
    
- **CsServerAdministrator:** メンバーは、サーバーを実行しているすべてのサーバーを管理、監視Skype for Business Server。
    
- **CsUserAdministrator:** メンバーは、ユーザーの管理、有効化および無効化、ユーザーへの既存ポリシーの割り当てを実行できます。
    
- **CsViewOnlyAdministrator:** メンバーは、サーバー情報の展開と構成を表示できます。 このメンバーシップを使用すると、メンバーはサーバーを実行しているサーバーの正常性をSkype for Business Server。
    
- **CsVoiceAdministrator:** メンバーは、音声関連の設定を作成、構成、および管理Skype for Business Server。
    
セキュリティと役割ベースのアクセス制御の整合性を維持するために、ユーザーが展開の管理で実行する役割を定義するグループにユーザーをSkype for Business Serverします。
  

