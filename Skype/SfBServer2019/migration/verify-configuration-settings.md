---
title: 構成設定の確認
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: サーバーの全体管理ストアがある内部コンピューター、または Skype for Business Server 2019 Core Components (OcsCore.msi) がインストールされている任意のドメインに参加しているコンピューターで、Skype for Business Server 2019 Get-CsManagementStoreReplicationStatus コマンドレットを実行して、エッジ サーバーへの構成情報のレプリケーションを検証できます。
ms.openlocfilehash: ff46dbad696ac4bf200bb669de768a28d0815e1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594265"
---
# <a name="verify-configuration-settings"></a>構成設定の確認

サーバーの全体管理ストアがある内部コンピューター、または Skype for Business Server 2019 Core Components (OcsCore.msi) がインストールされている任意のドメインに参加しているコンピューターで、Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** コマンドレットを実行することで、エッジ サーバーへの構成情報のレプリケーションを検証できます。 
  
最初の結果は、レプリケーションが "True" ではなく "False" の状態であると示される場合があります。その場合、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、時間をおいて、レプリケーションが完了してから再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。 
  

