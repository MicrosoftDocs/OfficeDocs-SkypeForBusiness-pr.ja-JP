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
description: Skype for business Server 2019 では、Skype for Business Server 2019 コンポーネントを含むネットワーク上のサイトを定義します。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752629"
---
# <a name="migration-phases"></a>移行フェーズ

Skype for business Server 2019 では、Skype for Business Server 2019 コンポーネントを含むネットワーク上のサイトを定義します。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。 
  
フロントエンドプールは、同一のユーザーグループに対してサービスを提供するために、同一に構成されたフロントエンドサーバーのセットです。 プールはユーザーにスケーラビリティとフェールオーバー機能をもたらします。 プール内の各サーバーでは、同一のサーバーの役割を実行する必要があります。 小規模な組織向けに設計された Standard Edition サーバーも、プールを定義し、単一のサーバー上で実行します。 これにより、Skype for Business Server 2019 の機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。 
  
次のフェーズでは、Skype for Business Server 2019 へのプールの移行プロセスについて説明します。 複数のプールで構成される複数のサイトの場合は、それぞれのプールに対して以下のフェーズの手順を適用する必要があります。
  
1. [フェーズ 1: 移行の計画](phase-1-plan-your-migration.md)
    
2. [フェーズ 2: 移行の準備](phase-2-prepare-for-migration.md)
    
3. [フェーズ 3: Skype for Business Server 2019 パイロットプールを展開する](phase-3-deploy-pilot-pool.md)
    
4. [フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [フェーズ 5: Skype for Business Server 2019 エッジサーバーをパイロットプールに追加する](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [フェーズ 6: パイロット展開から運用展開への移行](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [フェーズ 7: 移行後のタスクの実行](phase-7-complete-post-migration-tasks.md)
    
8. [フェーズ 8: レガシ プールの使用停止](phase-8-decommission-legacy-pools.md)
    

