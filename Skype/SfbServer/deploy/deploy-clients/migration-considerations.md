---
title: Skype Room System の移行に関する考慮事項
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: このトピックでは、複数のバージョンの Skype for Business Server および Lync Server を使用している環境に Skype Room システムを展開する方法について説明します。
ms.openlocfilehash: 6524a7312644ec306185b952caf17818d29344af
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774675"
---
# <a name="skype-room-system-migration-considerations"></a>Skype Room System の移行に関する考慮事項
 
このトピックでは、複数のバージョンの Skype for Business Server および Lync Server を使用している環境に Skype Room システムを展開する方法について説明します。
  
## <a name="migration-considerations"></a>移行に関する考慮事項

このセクションでは、さまざまなバージョンの Skype for Business Server (Lync Server) を含むマルチプール環境に Skype Room システムを展開する場合のガイダンスを示します。 
  
Lync Server のユーザー レプリケーター (UR) コンポーネントは、Active Directory からユーザー オブジェクトを取得し、それを Lync Server のバックエンドである SQL Server データベースに登録します。 Lync Server 2013 の UR のみが、Skype Room System オブジェクトを認識しています。 前のバージョンの Lync Server および Office Communications Server の UR は、LRS オブジェクトを指定する Active Directory 属性を検出しないため、認識もできません。 
  
Skype Room System アカウントが Lync にサインインしようとして、SRV レコードまたは DNS A レコードに基づいて自動検出を実行していて、それらのアカウントが以前のバージョンの Lync Server または Office Communications Server をポイントしている場合、LRS はから404が見つかりませんでした。 従来のプール。 従来のプールでは、Skype Room システムを Lync Server 2013 ホームプールにリダイレクトすることはできません。 
  
この問題は、次の方法で対応できます。 
  
- 自動検出 SRV レコード (_sipinternaltls._tcp.contoso.com) で Lync Server 2013 プールを参照させる。
    
- 最初のオプションが利用できない場合は、LRS を手動で構成して、Lync Server 2013 プールアドレスを提供する必要があります。 Skype Room System コンソールアプリケーションで直接構成します。 
    
- Skype Room System が企業ネットワークの外部に展開されていて、Lync Edge サーバーが展開されて、従来のプールまたはディレクターをポイントするように構成されている場合は、Lync Server 2013 プールを参照するセカンダリエッジサーバーサイトが必要です。 2 台目の Edge Server の展開に関する情報は、Edge Server の展開に関するドキュメントを参照してください。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Lync Server 2010 プールを使った Skype Room System の相互運用性

移行中に、Lync Server 2010 プールをホームにしているユーザーが会議をスケジュールし、Skype Room System アカウントを招待した場合、Skype Room System クライアントは、会議に出席するときに制限された機能を持つことになります。 
  
Skype Room System クライアントが、Lync Server 2010 を使っているユーザーによって開催されたスケジュールされた電話会議に参加すると、Skype Room System には以下の会議の制限があります。 
  
- Skype Room System では、マルチビュービデオギャラリーを表示できません。
    
- Skype Room System クライアントが発表者である場合、参加者にビデオロックを適用することはできません。
    
- Lync Server 2013 会議ポリシーで許可されている場合でも、次の理由により、1080p のビデオ解像度 (受信または送信) を表示できません。 
    
  - Lync Server 2010 は、1080p の解像度をサポートしていません。
    
  - Skype Room System は、ビデオ解像度の開催者の会議ポリシーによって常に制限されています。 したがって、Lync 2010 プールが720p の解像度をサポートしている場合でも、開催者のポリシーでサポートされていない限り、Skype Room システムは720p の解像度を利用することはできません。 
    
- Lync 2013 クライアントは、会議室の LRS プレゼンスを検出し、自動ミュートにより実際の会議室のエコーを回避します。この機能は、Lync Server 2010 でホストされている会議では動作しません。
    
- Lync Server 2010 でホストされている会議では、デスクトップ共有のパフォーマンスに制限が生じます。
    
- ユーザーは、Skype Room System で Lync 2010 上でホストされているプライベート (制限された) 会議に参加することはできません。
    

