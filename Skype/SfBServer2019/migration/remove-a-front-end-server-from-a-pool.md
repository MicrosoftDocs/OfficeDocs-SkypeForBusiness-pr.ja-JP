---
title: プールからのフロント エンド サーバーの削除
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
description: フロントエンド サーバーをスタンドアロン コンピューターとして存在することはできません。 プールにコンピューターが 1 台だけある場合でも、フロント エンド プールとして定義する必要があります。
ms.openlocfilehash: b52954421034d83191e479e59d1efeeda8972868
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595001"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>プールからのフロント エンド サーバーの削除

フロントエンド サーバーをスタンドアロン コンピューターとして存在することはできません。 プールにコンピューターが 1 台だけある場合でも、フロント エンド プールとして定義する必要があります。
  
このトピックでは、既存のフロント エンド プールから個々のフロント エンド サーバーを削除するプロセスについて説明します。 フロントエンド サーバーがプール内の最後のサーバーである場合、またはプールを完全に削除する場合は、「Remove Front End pool or Standard Edition[サーバー」を参照してください](remove-front-end-pool-or-standard-edition-server.md)。 フロントエンド プールを削除する前に、個々のフロントエンド サーバーを削除する必要はありません。 プールを削除すると、各フロント エンド サーバーが削除されます。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>フロントエンド サーバーをプールから削除するには

1. 2019 Skype for Business Server エンド サーバーで、トポロジ ビルダーを開きます。
    
2. 従来のインストール ノードに移動します。
    
3. [Enterprise Edition **フロントエンド** プール] を展開し、削除するフロント エンド サーバーを含むフロントエンド プールを展開し、削除するフロント エンド サーバーを右クリックし、[削除] をクリック **します**。
    

