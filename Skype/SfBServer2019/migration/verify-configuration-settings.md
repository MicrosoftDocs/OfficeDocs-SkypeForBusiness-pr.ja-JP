---
title: 構成の設定の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 中央管理ストアが配置されている内部コンピューターで、または任意の場所で Skype for Business Server 2019 CsManagementStoreReplicationStatus コマンドレットを実行して、構成情報のレプリケーションをエッジサーバーに対して検証することができます。Skype for Business Server 2019 コアコンポーネント (OcsCore) がインストールされているドメインに参加しているコンピューター。
ms.openlocfilehash: 5beb3c80bbc4c2f9a73fe68b9d99d7752598c680
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240939"
---
# <a name="verify-configuration-settings"></a>構成の設定の確認

中央管理ストアが配置されている内部コンピューターで Skype for Business Server 2019 **CsManagementStoreReplicationStatus**コマンドレットを実行して、構成情報のレプリケーションをエッジサーバーに対して検証することができます。Skype for Business Server 2019 コアコンポーネント (OcsCore) がインストールされている任意のドメインに参加しているコンピューターの場合。 
  
初期結果では、レプリケーションに "True" ではなく "False" と表示されることがあります。 その場合は、 **CsManagementStoreReplication**コマンドレットを実行して、 **CsManagementStoreReplicationStatus**をもう一度実行する前に複製処理が完了するまで待ちます。 
  

