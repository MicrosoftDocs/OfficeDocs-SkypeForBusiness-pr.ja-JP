---
title: Skype for Business Server 2019 への移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このセクションのトピックでは、Skype for Business Server 2019 への移行プロセスについて説明します。
ms.openlocfilehash: 8e58eaa3870e8149e874a1ec196a728976f429f3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237773"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Skype for Business Server 2019 への移行

このセクションのトピックでは、Skype for Business Server 2019 への移行プロセスについて説明します。 この記事では、Lync Server 2013 または Skype for business Server 2015 から Skype for Business Server 2019 への移行について説明します。

> [!IMPORTANT]
> このコンテンツ全体を通して、*従来*の Lync server 2013 または Skype For business server 2015 を使って、Skype For business server 2019 に移行していることを意味します。
  
> [!IMPORTANT]
> このガイドでは、移行の各フェーズを実行するために必要な手順について説明します。 これは、すべてのレガシ展開トポロジまたは可能な移行シナリオには対応していません。 このため、説明されている手順をすべて実行する必要がない場合や、展開によっては追加の手順を実行する必要がある場合があります。 このガイドでは、確認手順の例についても説明します。 この確認手順は、移行の進行に合わせて各フェーズが正常に完了するために必要な情報を確認するために用意されています。 この確認手順は、特定の移行プロセスに合わせて調整してください。 
  
このガイドには、既存の展開のアップグレードに固有の情報が記載されています。 既存のトポロジを変更する方法については説明しません。 このガイドでは、新機能の実装については説明しません。 詳細な手順については、このガイドの「記事または記事」で説明します。 
  
この記事では、次の一覧で指定された用語について説明します。
  
**移行:** Lync Server 2013 または Skype for business Server 2015 から運用展開を Skype for Business Server 2019 に移行します。
    
**共存:** 一部の機能が Skype for Business Server 2019 に移行されていて、その他の機能が以前のバージョンでも残っている場合、移行中に存在する一時的な環境。
    
**相互運用性:** 共存期間中に展開が正常に動作する能力。

**従来:** 移行元のシステムは、Lync Server 2013 または Skype for Business Server 2015 のいずれかです。
    
## <a name="in-this-section"></a>このセクションの内容

- [移行を始める前に](before-you-begin-the-migration.md)
    
- [フェーズ 1: 移行の計画](phase-1-plan-your-migration.md)
    
- [フェーズ 2: 移行の準備](phase-2-prepare-for-migration.md)
    
- [フェーズ 3: パイロット プールの展開](phase-3-deploy-pilot-pool.md)
    
- [フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [フェーズ 5: パイロット プールへのエッジ サーバーの追加](phase-5-add-edge-server-to-pilot-pool.md)
    
- [フェーズ 6: パイロット展開から運用展開への移行](phase-6-move-from-pilot-deployment-into-production.md)
    
- [フェーズ 7: 移行後のタスクの実行](phase-7-complete-post-migration-tasks.md)
    
- [フェーズ 8: レガシ プールの使用停止](phase-8-decommission-legacy-pools.md)
    

