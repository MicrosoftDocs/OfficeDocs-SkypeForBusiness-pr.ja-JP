---
title: 構成の設定を確認する
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
description: 中央管理ストアが配置されている内部コンピューターで、または Skype for Business Server 2019 コアコンポーネント (OcsCore.msi) がインストールされているドメインに参加しているコンピューターで、Skype for Business Server 2019 コマンドレットを実行することによって、エッジサーバーへの構成情報のレプリケーションを検証できます。
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752149"
---
# <a name="verify-configuration-settings"></a>構成の設定を確認する

中央管理ストアが配置されている内部コンピューターで、または Skype for business Server 2019 コアコンポーネント (OcsCore.msi) がインストールされている任意のドメインに参加しているコンピューターで、Skype for Business **server 2019 コマンド**レットを実行して、エッジサーバーへの構成情報のレプリケーションを検証できます。 
  
最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。 その場合、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、時間をおいて、レプリケーションが完了してから再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。 
  

