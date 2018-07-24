---
title: Skype Room System の移行に関する考慮事項
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: ビジネス サーバーと Lync Server の複数のバージョンの Skype を持つ環境で Skype ルームのシステムを展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 24015d85ef82b3a175564f92504d7c0ca46e9d54
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982749"
---
# <a name="skype-room-system-migration-considerations"></a>Skype Room System の移行に関する考慮事項
 
ビジネス サーバーと Lync Server の複数のバージョンの Skype を持つ環境で Skype ルームのシステムを展開する方法の詳細については、このトピックを参照してください。
  
## <a name="migration-considerations"></a>移行に関する考慮事項

このセクションでは、ビジネス サーバー、Lync Server では、Office 通信 Server 2007 の R2 の Skype のバージョンを含む複数のプール環境で Skype ルームのシステムを導入する場合のガイダンスを示します。 
  
Lync Server のユーザー レプリケーター (UR) コンポーネントは、Active Directory からユーザー オブジェクトを取得し、それを Lync Server のバックエンドである SQL Server データベースに登録します。 Skype ルームのシステム オブジェクトへの対応、Lync Server 2013 で UR のみです。 前のバージョンの Lync Server および Office Communications Server の UR は、LRS オブジェクトを指定する Active Directory 属性を検出しないため、認識もできません。 
  
Skype ルーム システム アカウントが Lync にサインインしようとすると、SRV レコード、または、DNS の A レコードの検索に基づく自動検出を実行し、それらのアカウントが Lync Server または Office Communications Server の以前のバージョンを指す場合、LRS は応答が 404 見つかりませんから 従来のプールです。 従来のプールは Skype ルームのシステムを Lync Server 2013 のホーム プールにリダイレクトすることができません。 
  
この問題は、次の方法で対応できます。 
  
- 自動検出 SRV レコード (_sipinternaltls._tcp.contoso.com) で Lync Server 2013 プールを参照させる。
    
- 最初のオプションが使用できない場合は、LRS を構成して Skype ルーム システムのコンソール アプリケーションで直接構成することによって、Lync Server 2013 プールのアドレスを提供する手動でする必要があります。 
    
- Skype ルーム システムは、企業ネットワークの外部展開し、Lync エッジ サーバーを展開し、従来のプールまたはディレクターを指すように構成されている、エッジ サーバーのセカンダリ サイトが必要な場合は、Lync Server 2013 プールを指します。 2 台目の Edge Server の展開に関する情報は、Edge Server の展開に関するドキュメントを参照してください。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Lync Server 2010 プールで Skype ルーム システムの相互運用性

移行中に、Lync Server 2010 プール上のホーム ユーザーは、会議をスケジュールし、Skype ルーム システム アカウントへの招待の場合 Skype ルーム システムのクライアントの機能が制限、ミーティングへの参加中に。 
  
Skype ルーム システム クライアント別に整理しているスケジュールされた電話会議に参加するときは、ユーザーが Lync Server 2010 のホーム、Skype ルームのシステムには次の会議での制限。 
  
- Skype ルーム システムは、複数のビューのビデオ ギャラリーを表示できません。
    
- Skype ルーム システムのクライアントが発表者の場合は、参加者のビデオのロックに適用できません。
    
- Skype ルーム システムは、場合でも、Lync Server 2013 の会議ポリシーは、次の理由により、1080 p ビデオの解像度 (受信または発信) を表示できません。 
    
  - Lync Server 2010 では、1080 p の解像度をサポートしていません。
    
  - Skype ルーム システムは、ビデオの解像度の開催者の会議のポリシーが常に制限されます。 したがって、Lync 2010 のプールでは、720 p の解像度をサポートする場合でも Skype ルーム システムできなく主催者のポリシーをサポートしていない限り、720 p の解像度を利用します。 
    
- Lync 2013 クライアントは、会議室の LRS プレゼンスを検出し、自動ミュートにより実際の会議室のエコーを回避します。この機能は、Lync Server 2010 でホストされている会議では動作しません。
    
- Lync Server 2010 でホストされている会議では、デスクトップ共有のパフォーマンスに制限が生じます。
    
- ユーザーはプライベート (制限された) 会議でホストされている Skype ルームのシステムと Lync 2010 に参加することはできません。
    

