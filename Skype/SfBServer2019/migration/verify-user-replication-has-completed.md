---
title: ユーザー レプリケーションの完了の確認
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Skype for Business Server 2019 データベース間のユーザー情報が同期されていないため、CsUser コマンドレットを実行しているときにエラーが発生することがあります。 Skype for Business Server 2019 のユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Skype for Business Server 2019 プールをホストしている Active Directory フォレスト内でホストされているドメインコントローラーの数によって異なります。 Skype for Business Server 2019 のユーザーレプリケーターサービスの初期同期処理は、Skype for business Server 2019 フロントエンドサーバーが初めて起動されたときに発生します。 それ以降は、ユーザー レプリケーターの間隔に基づいて同期が行われます。 Move-CsUser コマンドレットを実行する前に、次の手順を実行して、ユーザーのレプリケーションが完了していることを確認してください。
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751649"
---
# <a name="verify-user-replication-has-completed"></a>ユーザー レプリケーションの完了の確認

最初のレプリケーションが完了していないために、Active Directory ドメインサービス (AD DS) と Skype for Business Server 2019 データベースの間のユーザー情報が同期されていない場合、 **csuser**コマンドレットを実行すると障害が発生する可能性があります。 Skype for Business Server 2019 のユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Skype for Business Server 2019 プールをホストしている Active Directory フォレスト内でホストされているドメインコントローラーの数によって異なります。 Skype for Business Server 2019 のユーザーレプリケーターサービスの初期同期処理は、Skype for business Server 2019 フロントエンドサーバーが初めて起動されたときに発生します。 その後は、ユーザーレプリケーターの間隔に基づいて同期が実行されます。 次の手順を実行して、ユーザーのレプリケーションが完了したことを確認してから、 **csuser**コマンドレットを実行します。 
  
### <a name="to-verify-that-user-replication-has-completed"></a>ユーザーのレプリケーションが完了していることを確認するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. [**スタート**] メニューをクリックし、[**ファイル名を指定して実行**] をクリックします。 
    
3. 「**eventvwr.exe**」と入力し、[**OK**] をクリックします。
    
4. イベントビューアーで、[**アプリケーションとサービスログ**] をクリックして展開し、[Skype For business Server] を選択します。 
    
5. [**操作**] ウィンドウで [**現在のログをフィルター**] をクリックします。
    
6. [**イベント ソース**] ボックスの一覧の [**LS User Replicator**] をクリックします。
    
7. で **\<All Event IDs\>** 、 **30024**と入力し、[ **OK]** をクリックします。 
    
8. フィルター処理されたイベントの一覧の **[全般**] タブで、ユーザーのレプリケーションが正常に完了したことを示すエントリを探します。 
    

