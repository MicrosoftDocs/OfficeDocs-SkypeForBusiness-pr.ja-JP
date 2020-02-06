---
title: プールからのフロントエンド サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: フロントエンドサーバーは、スタンドアロンコンピューターとしては存在できません。 プールに1台のコンピュータしかない場合でも、フロントエンドプールとして定義する必要があります。
ms.openlocfilehash: 93df9e293f7a1876d4a8b1f172472f708556f67f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813035"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>プールからのフロントエンド サーバーの削除

フロントエンドサーバーは、スタンドアロンコンピューターとしては存在できません。 プールに1台のコンピュータしかない場合でも、フロントエンドプールとして定義する必要があります。
  
このトピックでは、既存のフロントエンドプールから個々のフロントエンドサーバーを削除する手順について説明します。 フロントエンドサーバーがプール内の最後のサーバーである場合、またはプールを完全に削除する場合は、「[フロントエンドプールまたは Standard Edition サーバーを削除](remove-front-end-pool-or-standard-edition-server.md)する」を参照してください。 フロントエンドプールを削除する前に、個々のフロントエンドサーバーを削除する必要はありません。 プールを削除すると、各フロントエンドサーバーが削除されます。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>プールからフロントエンドサーバーを削除するには

1. Skype for Business Server 2019 フロントエンドサーバーで、[トポロジビルダー] を開きます。
    
2. 従来のインストールノードに移動します。
    
3. [ **Enterprise Edition のフロントエンドプール**] を展開し、削除するフロントエンドサーバーでフロントエンドプールを展開して、削除するフロントエンドサーバーを右クリックし、[**削除**] をクリックします。
    

