---
title: 2019 Skype for Business Serverへの移行
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
description: このセクションのトピックでは、2019 年から 2019 年Skype for Business Server説明します。
ms.openlocfilehash: 1014fe5d491823c427eb588aac86757afb997578b519abf2249f481c91a3d4aa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303401"
---
# <a name="migration-to-skype-for-business-server-2019"></a>2019 Skype for Business Serverへの移行

このセクションのトピックでは、2019 年から 2019 年Skype for Business Server説明します。 この記事では、Lync Server 2013 または 2015 Skype for Business Server 2019 Skype for Business Serverについて説明します。

> [!IMPORTANT]
> コンテンツ全体で、従来の用語を使用して、従来の Lync Server 2013 または Skype for Business Server 2015 を参照して、Skype for Business Server 2019 に移行します。
  
> [!IMPORTANT]
> このガイドでは、移行の各フェーズを実行するために一般的に必要な手順について説明します。 この手順は、考え得るすべての従来の展開トポロジやすべての移行シナリオに対応するものではありません。 したがって、展開によっては、記載されているすべての手順を実行する必要がない場合や、追加の手順が必要になる場合があります。 このガイドでは、検証手順の例も示します。 検証手順を見ることによって、移行の作業を進める過程で各フェーズが正常に完了したことを確認するために何を調べる必要があるかを理解できるようになります。 各自の移行プロセスに合わせてこれらの検証手順を変更してください。 
  
このガイドでは、既存の展開をアップグレードする方法についてのみ説明します。 既存のトポロジを変更する方法については説明しません。 また、このガイドでは新しい機能の実装については説明しません。 詳細な手順が他の場所に記載されている場合は、このガイドから記事または記事セクションに移動します。 
  
この記事では、次の一覧で指定されている用語を定義します。
  
**移行:** 実稼働展開を Lync Server 2013 または 2015 Skype for Business Serverから 2019 Skype for Business Serverします。
    
**共存:** 一部の機能が Skype for Business Server 2019 に移行され、その他の機能が以前のバージョンに残っている場合、移行中に存在する一時的な環境。
    
**相互運用性:** 共存期間中に展開が正常に動作する機能。

**レガシ:** 移行先のシステム (Lync Server 2013 または 2015 Skype for Business Serverです。
    
## <a name="in-this-section"></a>このセクションの内容

- [移行を始める前に](before-you-begin-the-migration.md)
    
- [フェーズ 1: 移行の計画](phase-1-plan-your-migration.md)
    
- [フェーズ 2: 移行の準備](phase-2-prepare-for-migration.md)
    
- [フェーズ 3: パイロット プールの展開](phase-3-deploy-pilot-pool.md)
    
- [フェーズ 4: テスト ユーザーをパイロット プールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [フェーズ 5: パイロット プールへのエッジ サーバーの追加](phase-5-add-edge-server-to-pilot-pool.md)
    
- [フェーズ 6: パイロット展開から運用展開への移行](phase-6-move-from-pilot-deployment-into-production.md)
    
- [フェーズ 7: 移行後のタスクの実行](phase-7-complete-post-migration-tasks.md)
    
- [フェーズ 8: レガシ プールの使用停止](phase-8-decommission-legacy-pools.md)
    

