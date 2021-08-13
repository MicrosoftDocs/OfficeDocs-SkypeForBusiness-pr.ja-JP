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
description: Move-CsUser コマンドレットを実行すると、Active Directory ドメイン サービス (AD DS) と Skype for Business Server 2019 データベース間のユーザー情報が同期しないので、初期レプリケーションが不完全のため、エラーが発生する可能性があります。 Skype for Business Server 2019 User Replicator サービスの初期同期が正常に完了するのにかかる時間は、Skype for Business Server 2019 プールをホストする Active Directory フォレストでホストされているドメイン コントローラーの数によって異なります。 2019 Skype for Business Server 2019 ユーザー レプリケーター サービスの初期同期プロセスは、Skype for Business Server 2019 フロントエンド サーバーが初めて開始された場合に発生します。 それ以降は、ユーザー レプリケーターの間隔に基づいて同期が行われます。 Move-CsUser コマンドレットを実行する前に、次の手順を実行して、ユーザーのレプリケーションが完了していることを確認してください。
ms.openlocfilehash: 0fe1c205b04ed32f5ac4281e555d5a44262905aa23b74eb69148d447337b59f7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325684"
---
# <a name="verify-user-replication-has-completed"></a>ユーザー レプリケーションの完了の確認

**Move-CsUser** コマンドレットを実行すると、Active Directory ドメイン サービス (AD DS) と Skype for Business Server 2019 データベース間のユーザー情報が同期しないので、初期レプリケーションが不完全な場合にエラーが発生する可能性があります。 Skype for Business Server 2019 User Replicator サービスの初期同期が正常に完了するのにかかる時間は、Skype for Business Server 2019 プールをホストする Active Directory フォレストでホストされているドメイン コントローラーの数によって異なります。 2019 Skype for Business Server 2019 ユーザー レプリケーター サービスの初期同期プロセスは、Skype for Business Server 2019 フロントエンド サーバーが初めて開始された場合に発生します。 その後、同期はユーザー レプリケーター間隔に基づいて行います。 **Move-CsUser** コマンドレットを実行する前に、次の手順を実行して、ユーザー レプリケーションが完了したと確認します。 
  
### <a name="to-verify-that-user-replication-has-completed"></a>ユーザーのレプリケーションが完了していることを確認するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. [**スタート**] メニューをクリックし、[**ファイル名を指定して実行**] をクリックします。 
    
3. 「**eventvwr.exe**」と入力し、[**OK**] をクリックします。
    
4. イベント ビューアーで、[**アプリケーションとサービス**] ログをクリックして展開し、[アプリケーション とサービス] Skype for Business Server。 
    
5. [**操作**] ウィンドウで [**現在のログをフィルター**] をクリックします。
    
6. [**イベント ソース**] ボックスの一覧の [**LS User Replicator**] をクリックします。
    
7. で **\<All Event IDs\>** **、30024 と入力** し **、[OK] をクリックします**。 
    
8. フィルター処理されたイベントの一覧の[全般] タブで、ユーザー レプリケーションが正常に完了したと示すエントリを探します。 
    

