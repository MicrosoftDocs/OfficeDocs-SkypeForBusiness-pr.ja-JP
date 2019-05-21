---
title: 移行のフェーズ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 では、Skype for business Server 2019 コンポーネントが含まれているネットワーク上のサイトを定義します。 サイトは、単一のローカルエリアネットワーク (LAN)、または高速の光ファイバーネットワークによって接続された2つのネットワークなど、高速で待機時間の短いネットワークによって適切に接続されたコンピューターのセットです。
ms.openlocfilehash: 8f50f25536e330a03440702614f81c09ce74518a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298163"
---
# <a name="migration-phases"></a>移行のフェーズ

Skype for Business Server 2019 では、Skype for business Server 2019 コンポーネントが含まれているネットワーク上のサイトを定義します。 サイトは、単一のローカルエリアネットワーク (LAN)、または高速の光ファイバーネットワークによって接続された2つのネットワークなど、高速で待機時間の短いネットワークによって適切に接続されたコンピューターのセットです。 
  
フロントエンドプールは、共通のユーザーグループに対してサービスを提供するために、同じように構成され、連携して動作するフロントエンドサーバーのセットです。 プールにより、ユーザーにスケーラビリティとフェールオーバー機能が提供されます。 プール内の各サーバーは同じサーバーの役割を実行する必要があります。 小規模の組織向けに設計された Standard Edition サーバーでは、プールを定義し、単一のサーバーで実行することもできます。 これにより、Skype for Business Server の2019機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。 
  
以下のフェーズでは、Skype for Business Server 2019 へのプール移行のプロセスについて説明します。 複数のプールを含む複数のサイトの場合、個々のプールはこの段階的なアプローチに従う必要があります。
  
1. [フェーズ 1: 移行の計画](phase-1-plan-your-migration.md)
    
2. [フェーズ 2: 移行の準備](phase-2-prepare-for-migration.md)
    
3. [フェーズ 3: Skype for Business Server 2019 パイロットプールの展開](phase-3-deploy-pilot-pool.md)
    
4. [フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [フェーズ 5: Skype for Business Server 2019 エッジサーバーをパイロットプールに追加する](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [フェーズ 6: パイロット展開から運用展開への移行](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [フェーズ 7: 移行後のタスクの実行](phase-7-complete-post-migration-tasks.md)
    
8. [フェーズ 8: レガシ プールの使用停止](phase-8-decommission-legacy-pools.md)
    

