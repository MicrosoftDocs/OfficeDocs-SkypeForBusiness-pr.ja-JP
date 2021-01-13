---
title: Skype for Business Server コントロール パネル管理者の作成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: Skype for Business Server 2015 へのアクセスを許可するには、次の操作を行います。
ms.openlocfilehash: 40c119f99182dc2416a1414db2a2fc143e818352
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811077"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Skype for Business Server コントロール パネル管理者の作成
 
Skype for Business Server 2015 へのアクセスを許可するには、次の操作を行います。
  
1. Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. [**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーを右クリックし、[**プロパティ**] をクリックします。
    
3. [**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。
    
4. [メンバー] タブで [**追加**] をクリックします。[**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。CSAdministrators グループに追加するユーザー名またはグループ名を入力します。[**OK**] をクリックします。
    
5. [メンバー] タブで、選択したユーザーまたはグループが表示されていることを確認します。[**OK**] をクリックします。
    
> [!TIP]
> Skype for Business Server コントロール パネルは、役割ベースのアクセス制御ツールです。 CsAdministrator グループのメンバーシップにより、Skype for Business Server コントロール パネルを使用しているユーザーは、使用可能なすべての構成機能を完全に制御できます。 特定の機能向けに設計されたその他の役割も使用できます。 ユーザーが管理グループのメンバーになるには、Skype for Business Server を有効にする必要があります。 
  
その他の役割は次のとおりです。
  
- **CsArchiving:** このグループのメンバーは、アーカイブ サーバーの役割の構成や管理など、すべてのアーカイブ機能を実行できます。
    
- **CsHelpDesk:** このグループのメンバーは、ユーザーのプロパティやポリシーを含む構成と展開を表示できます。またメンバーは、特定のトラブルシューティング タスクも実行できます。
    
- **CsLocationAdministrator:** メンバーは、Enhanced 9-1-1 (E9-1-1) の管理と関連付けられた最小限のユーザー権限を持ちます。E9-1-1 の場所およびネットワーク識別子を作成し、展開内でそれらを関連付けることができます。
    
- **CsResponseGroupAdministrator:** メンバーは、応答グループ サービスを管理および構成できます。
    
- **CsServerAdministrator:** メンバーは、Skype for Business Server を実行しているすべてのサーバーを管理、監視、およびトラブルシューティングできます。
    
- **CsUserAdministrator:** メンバーは、ユーザーの管理、有効化および無効化、ユーザーへの既存ポリシーの割り当てを実行できます。
    
- **CsViewOnlyAdministrator:** メンバーは、サーバー情報の展開と構成を表示できます。 このメンバーシップにより、メンバーは Skype for Business Server 2015 を実行しているサーバーの正常性を監視できます。
    
- **CsVoiceAdministrator:** メンバーは、Skype for Business Server で音声関連の設定を作成、構成、および管理できます。
    
セキュリティと役割ベースのアクセス制御の整合性を維持するために、Skype for Business Server 展開の管理でユーザーが実行する役割を定義するグループにユーザーを追加します。
  

