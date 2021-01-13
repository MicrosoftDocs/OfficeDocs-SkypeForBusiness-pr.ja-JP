---
title: Skype Room System の移行に関する考慮事項
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
description: このトピックでは、Skype for Business Server と Lync Server の複数のバージョンを持つ環境に Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805787"
---
# <a name="skype-room-system-migration-considerations"></a>Skype Room System の移行に関する考慮事項
 
このトピックでは、Skype for Business Server と Lync Server の複数のバージョンを持つ環境に Skype Room System を展開する方法について説明します。
  
## <a name="migration-considerations"></a>移行に関する考慮事項

このセクションでは、異なるバージョンの Skype for Business Server または Lync Server を含むマルチプール環境に Skype Room System を展開する場合のガイダンスを提供します。 
  
Lync Server のユーザー レプリケーター (UR) コンポーネントは、Active Directory からユーザー オブジェクトを取得し、それらを Lync Server のバック エンド SQL Serverします。 Lync Server 2013 の UR だけが Skype Room System オブジェクトを認識します。 以前のバージョンの Lync Server および Office Communications Server の UR は、LRS オブジェクトを指定する Active Directory 属性を検出し、認識していなくためです。 
  
Skype Room System アカウントが Lync にサインインしようとして、SRV レコードまたは DNS A レコードの検索に基づいて自動検出を実行し、それらのアカウントが以前のバージョンの Lync Server または Office Communications Server をポイントしている場合、LRS はレガシ プールから 404 Not Found 応答を受信します。 従来のプールでは、Skype Room System を Lync Server 2013 ホーム プールにリダイレクトできません。 
  
この問題に対処するには、次のオプションを使用します。 
  
- 自動検出 SRV レコード (_sipinternaltls._tcp.contoso.com) を Lync Server 2013 プールの接続ポイントにします。
    
- 最初のオプションを使用できない場合は、LRS を手動で構成し、Skype Room System コンソール アプリケーションで直接構成して Lync Server 2013 プール アドレスを指定する必要があります。 
    
- Skype Room System が企業ネットワークの外部に展開され、Lync エッジ サーバーが展開され、従来のプールまたはディレクターをポイントするように構成されている場合は、Lync Server 2013 プールを指すセカンダリ エッジ サーバー サイトが必要です。 セカンダリ エッジ サーバーの展開の詳細については、エッジ サーバーの展開に関するドキュメントを参照してください。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype Room System と Lync Server 2010 プールの相互運用性

移行中に、Lync Server 2010 プールにホームを持つユーザーが会議をスケジュールし、Skype Room System アカウントを招待した場合、Skype Room System クライアントは会議への出席中に機能が制限されます。 
  
Skype Room System クライアントが、Lync Server 2010 にホームであるユーザーによって開催されたスケジュールされた電話会議に参加する場合、Skype Room System には次の会議中の制限があります。 
  
- Skype Room System では、マルチビュー ビデオ ギャラリーを表示できません。
    
- Skype Room System クライアントが発表者の場合、参加者にビデオ ロックを適用できません。
    
- 次の理由により、Lync Server 2013 会議ポリシーで許可されている場合でも、Skype Room System は 1080p ビデオ解像度 (受信または送信) を表示できません。 
    
  - Lync Server 2010 は、1080p の解像度をサポートしません。
    
  - Skype Room System は、ビデオの解決に関する開催者の会議ポリシーによって常に制限されます。 したがって、Lync 2010 プールが 720p の解像度をサポートしている場合でも、開催者のポリシーでサポートされていない限り、Skype Room System では 720p の解像度を利用できない可能性があります。 
    
- Lync 2013 クライアントは会議室内の LRS プレゼンスを検出し、物理的な会議室でのエコーを回避するために自身を自動ミュートします。 この機能は、Lync Server 2010 でホストされている会議では機能しません。
    
- Lync Server 2010 でホストされる会議のデスクトップ共有のパフォーマンスには制限があります。
    
- ユーザーは、Skype Room System を使用して Lync 2010 でホストされているプライベート (制限付き) 会議に参加できない。
    

