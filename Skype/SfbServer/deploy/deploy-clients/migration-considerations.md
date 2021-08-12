---
title: SkypeRoom System の移行に関する考慮事項
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: このトピックでは、複数のバージョンの Skypeと Lync Server を持つ環境にルーム システムを展開するSkype for Business Server説明します。
ms.openlocfilehash: bcbb8a14cf1d998c68f83875bce25935d73e92b7a755cd370526a65aef202e36
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310046"
---
# <a name="skype-room-system-migration-considerations"></a>SkypeRoom System の移行に関する考慮事項
 
このトピックでは、複数のバージョンの Skypeと Lync Server を持つ環境にルーム システムを展開するSkype for Business Server説明します。
  
## <a name="migration-considerations"></a>移行に関する考慮事項

このセクションでは、異なるバージョンの Skype または Lync Server を含むマルチプール環境に Skype for Business Server Room System を展開する場合のガイダンスを提供します。 
  
Lync Server のユーザー レプリケーター (UR) コンポーネントは、Active Directory からユーザー オブジェクトを取得し、それらを Lync Server のバック エンド SQL Serverします。 Lync Server 2013 の UR だけが、Room System オブジェクトSkype認識します。 以前のバージョンの Lync Server および Office Communications Server の UR では、LRS オブジェクトを指定する Active Directory 属性が検出されないので、その属性は認識されません。 
  
Skype Room System アカウントが Lync にサインインしようとして、SRV レコードまたは DNS A レコード検索に基づいて自動検出を実行し、それらのアカウントが以前のバージョンの Lync Server または Office Communications Server を指している場合、LRS はレガシ プールから 404 Not Found 応答を受信します。 従来のプールでは、ルーム システムSkype Lync Server 2013 ホーム プールにリダイレクトできません。 
  
この問題に対処するには、次のオプションを使用します。 
  
- 自動検出 SRV レコード (_sipinternaltls._tcp.contoso.com) を Lync Server 2013 プールにポイントします。
    
- 最初のオプションが使用できない場合は、LRS を手動で構成し、Skype Room System コンソール アプリケーションで直接構成して Lync Server 2013 プール アドレスを指定する必要があります。 
    
- Skype Room System が企業ネットワークの外部に展開され、Lync Edge Server が展開され、従来のプールまたはディレクターをポイントするように構成されている場合は、セカンダリ エッジ サーバー サイトが必要です。これは Lync Server 2013 プールを指しています。 セカンダリ エッジ サーバーの展開の詳細については、エッジ サーバーの展開に関するドキュメントを参照してください。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>SkypeLync Server 2010 プールとのルーム システムの相互運用性

移行中に、Lync Server 2010 プールに参加しているユーザーが会議をスケジュールし、Skype Room System アカウントを招待した場合、Skype Room System クライアントは会議に出席する際に機能が制限されます。 
  
Skype Room System クライアントが、Lync Server 2010 に参加しているユーザーによって組織された予定された電話会議に参加すると、Skype Room System には次の会議内の制限があります。 
  
- SkypeRoom System では、マルチビュー ビデオ ギャラリーを表示できません。
    
- Room System クライアントSkype発表者である場合、参加者にビデオ ロックを適用できません。
    
- SkypeRoom System では、Lync Server 2013 会議ポリシーで許可されている場合でも、次の理由で 1080p ビデオ解像度 (受信または送信) を表示できません。 
    
  - Lync Server 2010 は 1080p の解決をサポートしません。
    
  - Skypeルーム システムは、ビデオ解決のための開催者の会議ポリシーによって常に制限されます。 そのため、Lync 2010 プールが 720p 解決をサポートしている場合でも、Skype Room System は、開催者のポリシーがサポートしていない限り、720p の解像度を利用できない可能性があります。 
    
- Lync 2013 クライアントは会議室での LRS プレゼンスを検出し、物理的な会議室でのエコーを回避するために自分自身を自動ミュートします。 この機能は、Lync Server 2010 でホストされている会議では機能しません。
    
- Lync Server 2010 でホストされる会議のデスクトップ共有パフォーマンスには制限があります。
    
- ユーザーは、Lync 2010 でホストされているプライベート (制限付き) 会議に参加Skypeされません。
    

