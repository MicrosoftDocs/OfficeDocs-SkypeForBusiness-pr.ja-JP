---
title: フロントエンド プールまたは Standard Edition サーバーの削除
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
description: このトピックでは、フロントエンドプールまたは標準エディションのフロントエンドサーバーを削除する手順について説明します。 フロントエンドプールを削除する場合は、プールに属している各フロントエンドサーバーをプール削除プロセスの一部として削除します。 Standard Edition のフロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストアの定義を削除する必要があります。
ms.openlocfilehash: d3397b47f94a96cde3326b2479a9e5c6ffd365e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813005"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>フロントエンド プールまたは Standard Edition サーバーの削除

この記事では、フロントエンドプールまたは標準エディションのフロントエンドサーバーを削除するプロセスについて説明します。 フロントエンドプールを削除する場合は、プールに属している各フロントエンドサーバーをプール削除プロセスの一部として削除します。 Standard Edition のフロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストアの定義を削除する必要があります。
  
## <a name="to-remove-a-front-end-server-pool"></a>フロントエンドサーバープールを削除するには

1. トポロジビルダーを開きます。
    
2. 従来のノードに移動します。
    
3. **Enterprise Edition のフロントエンド**プールを展開し、フロントエンドプールを展開して、削除するフロントエンドプールを右クリックし、[**削除**] をクリックします。
    
4. トポロジを公開し、レプリケーションの状態を確認します。次に、必要に応じて従来の展開ウィザードを実行します。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Standard Edition フロントエンドサーバーを削除するには

1. トポロジビルダーを開きます。
    
2. 従来のインストールノードに移動します。
    
3. **Standard Edition のフロントエンド**サーバーを展開し、削除するフロントエンドサーバーを右クリックして、[**削除**] をクリックします。
    
4. [ **Sql ストア**] を展開し、Standard Edition フロントエンドサーバーに関連付けられている sql Server データベースを右クリックし、[**削除**] をクリックします。
    
    > [!IMPORTANT]
    > 併置された SQL Server データベースの定義は、Standard Edition のフロントエンドサーバーから削除する必要があります。 
  
5. トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて展開ウィザードを実行します。 
    

