---
title: 移行フェーズ
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
description: 2019 Skype for Business Serverでは、2019 コンポーネントを含むサイトをネットワークSkype for Business Serverします。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。
ms.openlocfilehash: 0e79dca32a0e3c377eea8e60e0e19514dcb7f4dfb459922b68c9913f4bd3c363
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303421"
---
# <a name="migration-phases"></a>移行フェーズ

2019 Skype for Business Serverでは、2019 コンポーネントを含むサイトをネットワークSkype for Business Serverします。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。 
  
フロントエンド プールは、同一に構成され、共通のユーザー グループにサービスを提供するために一緒に動作する一連のフロント エンド サーバーです。 プールはユーザーにスケーラビリティとフェールオーバー機能をもたらします。 プール内の各サーバーでは、同一のサーバーの役割を実行する必要があります。 小規模Standard Edition用に設計されたサーバーは、プールも定義し、1 つのサーバーで実行します。 これにより、2019 Skype for Business Server機能を使用してコストを削減できますが、真の高可用性ソリューションは提供されないのです。 
  
次のフェーズでは、2019 年にプールを移行Skype for Business Serverします。 複数のプールで構成される複数のサイトの場合は、それぞれのプールに対して以下のフェーズの手順を適用する必要があります。
  
1. [フェーズ 1: 移行の計画](phase-1-plan-your-migration.md)
    
2. [フェーズ 2: 移行の準備](phase-2-prepare-for-migration.md)
    
3. [フェーズ 3: 2019 パイロット Skype for Business Serverを展開する](phase-3-deploy-pilot-pool.md)
    
4. [フェーズ 4: テスト ユーザーをパイロット プールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [フェーズ 5: パイロット プールSkype for Business Server 2019 エッジ サーバーを追加する](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [フェーズ 6: パイロット展開から運用展開への移行](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [フェーズ 7: 移行後のタスクの実行](phase-7-complete-post-migration-tasks.md)
    
8. [フェーズ 8: レガシ プールの使用停止](phase-8-decommission-legacy-pools.md)
    

