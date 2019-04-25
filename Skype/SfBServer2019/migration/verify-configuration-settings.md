---
title: 構成の設定の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 中央管理ストアに保存されている、またはいずれかの内部コンピューターの CsManagementStoreReplicationStatus-ビジネス サーバー 2019 Get コマンドレットの Skype を実行して、エッジ サーバーの構成情報のレプリケーションを検証することができます。ビジネス サーバー 2019 のコア ・ コンポーネント (OcsCore.msi) の Skype がインストールされているコンピューターをドメインに参加します。
ms.openlocfilehash: 1b64569ffbdce3d7f41e7f6c54815d051848cfd1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231358"
---
# <a name="verify-configuration-settings"></a>構成の設定の確認

中央管理ストアに配置されて、内部コンピューターのビジネス サーバー 2019 **Get CsManagementStoreReplicationStatus**コマンドレットの Skype を実行して、エッジ サーバーに構成情報のレプリケーションを検証することができますかドメインに参加しているコンピューターはビジネス サーバー 2019 のコア ・ コンポーネント (OcsCore.msi) の Skype がインストールされています。 
  
初期結果可能性があります状態"False"と"True"ではなくレプリケーション用です。 場合は、**呼び出し CsManagementStoreReplication**コマンドレットを実行し、 **Get CsManagementStoreReplicationStatus**をもう一度実行する前に完了するのには、レプリケーションの時間を確保します。 
  

