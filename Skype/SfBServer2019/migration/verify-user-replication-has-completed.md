---
title: ユーザー レプリケーションの完了の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 移動-CsUser コマンドレットを実行しているときに、最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Skype for Business Server 2019 データベース間のユーザー情報が同期されていないため、エラーが発生する可能性があります。 Skype for Business Server 2019 ユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Skype for Business をホストしている Active Directory フォレストでホストされているドメインコントローラーの数によって異なります。サーバー2019プール。 Skype for Business Server 2019 ユーザーレプリケーターサービスの初期同期処理は、Skype for Business Server 2019 フロントエンドサーバーが初めて起動したときに発生します。 その後、同期はユーザーレプリケーターの間隔に基づいています。 次の手順を実行して、ユーザーの複製が完了したことを確認してから、移動-CsUser コマンドレットを実行します。
ms.openlocfilehash: d5d0462ec2886c73fb7286860eea2c89e0fea9fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280647"
---
# <a name="verify-user-replication-has-completed"></a>ユーザー レプリケーションの完了の確認

**移動-csuser**コマンドレットを実行しているときに、最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Skype For business Server 2019 データベースの間でユーザー情報が同期されていない場合、エラーが発生する可能性があります。 Skype for Business Server 2019 ユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Skype for Business をホストしている Active Directory フォレストでホストされているドメインコントローラーの数によって異なります。サーバー2019プール。 Skype for Business Server 2019 ユーザーレプリケーターサービスの初期同期処理は、Skype for Business Server 2019 フロントエンドサーバーが初めて起動したときに発生します。 その後、同期はユーザーレプリケーターの間隔に基づいています。 次の手順を実行して、ユーザーの複製が完了していることを確認してから、 **csuser**コマンドレットを実行します。 
  
### <a name="to-verify-that-user-replication-has-completed"></a>ユーザーの複製が完了したことを確認するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. [**スタート**] メニューをクリックし、[**実行**] をクリックします。 
    
3. **Eventvwr.exe**と入力して、[ **OK]** をクリックします。
    
4. イベントビューアーで [**アプリケーションとサービスログ**] をクリックして展開し、[Skype For business Server] を選択します。 
    
5. [**操作**] ウィンドウで、[**現在のログをフィルター**] をクリックします。
    
6. [**イベントソース**] ボックスの一覧の [ **LS ユーザーレプリケーター**] をクリックします。
    
7. ** \<すべてのイベント id\>** で「 **30024**」と入力して、[ **OK]** をクリックします。 
    
8. [フィルター処理されたイベント] ボックスの一覧の **[全般**] タブで、ユーザーの複製が正常に完了したことを示すエントリを探します。 
    

