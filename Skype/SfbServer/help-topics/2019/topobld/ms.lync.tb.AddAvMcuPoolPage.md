---
title: 音声ビデオ MCU プールの追加
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: すべてエンタープライズ エディション フロント エンド サーバーのセントラル サイトに配置されている必要はありませんが A V 会議サービスの使用同じスタンドアロン A/V 会議のプールです。 各 A の V 会議のプール、プールおよび A は 1 つだけ必要があるかどうかの完全修飾ドメイン名 (FQDN) を指定する必要があります V 会議サーバーまたは複数の負荷分散/A/V 会議サーバーです。
ms.openlocfilehash: f88476165ce6affe23e9e5cbb33e03a997c04971
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202304"
---
# <a name="add-av-mcu-pool"></a>音声ビデオ MCU プールの追加
 
すべてエンタープライズ エディション フロント エンド サーバーのセントラル サイトに配置されている必要はありませんが A V 会議サービスの使用同じスタンドアロン A/V 会議のプールです。 各 A の V 会議のプール、プールおよび A は 1 つだけ必要があるかどうかの完全修飾ドメイン名 (FQDN) を指定する必要があります V 会議サーバーまたは複数の負荷分散/A/V 会議サーバーです。
  
> [!IMPORTANT]
> 単一サーバー プールは、複数サーバーのプールに変換できません。 後で、組織が複数のサーバー プールを必要がある場合、1 台のサーバー プールを削除し、複数のサーバー プールを追加します。 
  
> [!TIP]
> A の実装を計画する場合は、/V 会議のプールは、今後、**複数コンピューターのプール**を選択します。 プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。 トポロジ ビルダーは、新しいプールのメンバーを定義し、新しいトポロジを公開し、新しい A をセットアップしをもう一度行う必要がありますより多くのコンピューターを後でプールに追加する準備ができたら、V 会議ビジネス サーバーの展開ウィザードの Skype を通じてメンバーをプールするとします。 A/V 会議サーバー プール一意する必要がありますを読み込まないようにプールを作成することにします。 A/V 会議プール内部での負荷を分散し、ハードウェアを追加する必要はありません。 
  

