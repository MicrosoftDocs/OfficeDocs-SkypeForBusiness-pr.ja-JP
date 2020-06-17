---
title: プールからのフロントエンド サーバーの削除
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
description: フロントエンドサーバーは、スタンドアロンのコンピューターとしては存在できません。 プール内にコンピューターが1台しかない場合でも、フロントエンドプールとして定義する必要があります。
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752319"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>プールからのフロントエンド サーバーの削除

フロントエンドサーバーは、スタンドアロンのコンピューターとしては存在できません。 プール内にコンピューターが1台しかない場合でも、フロントエンドプールとして定義する必要があります。
  
このトピックでは、既存のフロントエンドプールから個々のフロントエンドサーバーを削除するプロセスについて手順を追って説明します。 フロントエンドサーバーがプール内の最後のサーバーである場合、またはプールを完全に削除する場合は、「 [Remove Front end pool Or Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)」を参照してください。 フロントエンドプールを削除する前に、個々のフロントエンドサーバーを削除する必要はありません。 プールを削除すると、各フロントエンドサーバーが削除されます。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>フロントエンド サーバーをプールから削除するには

1. Skype for Business Server 2019 フロントエンドサーバーで、トポロジビルダーを開きます。
    
2. 従来のインストールノードに移動します。
    
3. [ **Enterprise Edition フロントエンドプール**] を展開し、削除するフロントエンドサーバーのフロントエンドプールを展開して、削除するフロントエンドサーバーを右クリックし、[**削除**] をクリックします。
    

