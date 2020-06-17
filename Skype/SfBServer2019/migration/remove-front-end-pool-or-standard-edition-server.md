---
title: フロントエンド プールまたは Standard Edition サーバーの削除
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
description: このトピックでは、フロントエンドプールまたは Standard Edition フロントエンドサーバーを削除するプロセスについて説明します。 フロントエンドプールを削除する場合は、プール削除処理の一部として、そのプールに属する各フロントエンドサーバーを削除します。 Standard Edition フロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストア定義を削除する必要があります。
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752279"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>フロントエンド プールまたは Standard Edition サーバーの削除

この記事では、フロントエンドプールまたは Standard Edition フロントエンドサーバーを削除するプロセスについて説明します。 フロントエンドプールを削除する場合は、プール削除処理の一部として、そのプールに属する各フロントエンドサーバーを削除します。 Standard Edition フロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストア定義を削除する必要があります。
  
## <a name="to-remove-a-front-end-server-pool"></a>フロントエンド サーバー プールを削除するには

1. トポロジ ビルダーを開きます。
    
2. 従来のノードに移動します。
    
3. [ **Enterprise Edition フロントエンド**プール] を展開し、フロントエンドプールを展開して、削除するフロントエンドプールを右クリックし、[**削除**] をクリックします。
    
4. トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて従来の展開ウィザードを実行します。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Standard Edition フロントエンド サーバーを削除するには

1. トポロジ ビルダーを開きます。
    
2. [従来のインストールのノードに移動します。
    
3. [ **Standard Edition フロントエンドサーバー**] を展開し、削除するフロントエンドサーバーを右クリックして、[**削除**] をクリックします。
    
4. [ **Sql ストア**] を展開し、Standard Edition フロントエンドサーバーに関連付けられている sql Server データベースを右クリックし、[**削除**] をクリックします。
    
    > [!IMPORTANT]
    > 併置された SQL Server データベースの定義は、Standard Edition フロントエンドサーバーから削除する必要があります。 
  
5. トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて展開ウィザードを実行します。 
    

