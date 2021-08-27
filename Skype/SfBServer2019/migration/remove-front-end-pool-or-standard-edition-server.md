---
title: フロント エンド プールまたは Standard Edition サーバーの削除
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
description: このトピックでは、フロントエンド プールまたはフロントエンド サーバーを削除するプロセスStandard Edition説明します。 フロントエンド プールを削除すると、プールの削除プロセスの一部として、プールに属する各フロントエンド サーバーを削除します。 フロントエンド サーバーから Standard Editionを削除する場合は、トポロジ ビルダーから SQLストア定義を削除する必要があります。
ms.openlocfilehash: 04ff2120fcbbe0c914a0a105669083eeb13a8347
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589251"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>フロント エンド プールまたは Standard Edition サーバーの削除

この記事では、フロントエンド プールまたはフロントエンド サーバーを削除するプロセスStandard Edition説明します。 フロントエンド プールを削除すると、プールの削除プロセスの一部として、プールに属する各フロントエンド サーバーを削除します。 フロントエンド サーバーから Standard Editionを削除する場合は、トポロジ ビルダーから SQLストア定義を削除する必要があります。
  
## <a name="to-remove-a-front-end-server-pool"></a>フロントエンド サーバー プールを削除するには

1. トポロジ ビルダーを開きます。
    
2. 従来のノードに移動します。
    
3. [Enterprise Edition **プール]** を展開し、[フロント エンド プール] を展開し、削除するフロントエンド プールを右クリックし、[削除] を **クリックします**。
    
4. トポロジを発行し、レプリケーションの状態を確認し、必要に応じて従来の展開ウィザードを実行します。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Standard Edition フロントエンド サーバーを削除するには

1. トポロジ ビルダーを開きます。
    
2. 従来のインストール ノードに移動します。
    
3. [Standard Edition **フロントエンド サーバー] を展開** し、削除するフロント エンド サーバーを右クリックし、[削除] を **クリックします**。
    
4. **[SQLストア]** を展開し、SQL Serverに関連付けられている Standard Edition データベースを右クリックし、[削除] をクリック **します**。
    
    > [!IMPORTANT]
    > フロント エンド サーバーから、SQL Serverデータベースの定義Standard Editionする必要があります。 
  
5. トポロジを公開し、レプリケーションの状態を確認し、必要に応じて展開ウィザードを実行します。 
    

