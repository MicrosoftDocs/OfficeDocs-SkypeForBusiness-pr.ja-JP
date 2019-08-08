---
title: プールからのフロントエンド サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フロントエンドサーバーは、スタンドアロンコンピューターとしては存在できません。 プールに1台のコンピュータしかない場合でも、フロントエンドプールとして定義する必要があります。
ms.openlocfilehash: 64f0c4134f690005815591bce88b8d058c1bd007
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244296"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>プールからのフロントエンド サーバーの削除

フロントエンドサーバーは、スタンドアロンコンピューターとしては存在できません。 プールに1台のコンピュータしかない場合でも、フロントエンドプールとして定義する必要があります。
  
このトピックでは、既存のフロントエンドプールから個々のフロントエンドサーバーを削除する手順について説明します。 フロントエンドサーバーがプール内の最後のサーバーである場合、またはプールを完全に削除する場合は、「[フロントエンドプールまたは Standard Edition サーバーを削除](remove-front-end-pool-or-standard-edition-server.md)する」を参照してください。 フロントエンドプールを削除する前に、個々のフロントエンドサーバーを削除する必要はありません。 プールを削除すると、各フロントエンドサーバーが削除されます。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>プールからフロントエンドサーバーを削除するには

1. Skype for Business Server 2019 フロントエンドサーバーで、[トポロジビルダー] を開きます。
    
2. 従来のインストールノードに移動します。
    
3. [ **Enterprise Edition のフロントエンドプール**] を展開し、削除するフロントエンドサーバーでフロントエンドプールを展開して、削除するフロントエンドサーバーを右クリックし、[**削除**] をクリックします。
    

