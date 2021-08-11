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
localization_priority: Normal
description: サーバーの全体管理ストアがある内部コンピューター、または Skype for Business Server 2019 Core Components (OcsCore.msi) がインストールされている任意のドメインに参加しているコンピューターで、Skype for Business Server 2019 Get-CsManagementStoreReplicationStatus コマンドレットを実行して、エッジ サーバーへの構成情報のレプリケーションを検証できます。
ms.openlocfilehash: e681781598af876f722094b0191aa784da2c533adc509a9f9fc4fad96fa4db4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335747"
---
# <a name="verify-configuration-settings"></a>構成設定の確認

サーバーの全体管理ストアがある内部コンピューター、または Skype for Business Server 2019 Core Components (OcsCore.msi) がインストールされている任意のドメインに参加しているコンピューターで、Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** コマンドレットを実行することで、エッジ サーバーへの構成情報のレプリケーションを検証できます。 
  
最初の結果は、レプリケーションが "True" ではなく "False" の状態であると示される場合があります。その場合、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、時間をおいて、レプリケーションが完了してから再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。 
  

