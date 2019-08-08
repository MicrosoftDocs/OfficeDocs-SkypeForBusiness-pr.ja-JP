---
title: 共通領域電話の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 一般的なエリア携帯電話は、共通のワークスペースや一般的な領域 (ロビー、台所、工場など) に存在する IP 電話です。 一般的なエリア携帯電話は、Skype for Business Server 統合通信 (UC) 機能を提供するためにコンピューターに接続する必要はありません。 展開を Skype for Business Server 2019 に移行した後は、従来の共通エリア電話に関連付けられた連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使用すると、従来の一般的なエリア電話に関連付けられたすべての連絡先オブジェクトが取得され、そのオブジェクトが Skype for Business Server 2019 プールに移動されます。
ms.openlocfilehash: 123f0a73da65e7d661541c6c4bec65481bf12f0c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238026"
---
# <a name="migrate-common-area-phones"></a>共通領域電話の移行

一般的なエリア携帯電話は、共通のワークスペースや一般的な領域 (ロビー、台所、工場など) に存在する IP 電話です。 一般的なエリア携帯電話は、Skype for Business Server 統合通信 (UC) 機能を提供するためにコンピューターに接続する必要はありません。 展開を Skype for Business Server 2019 に移行した後は、従来の共通エリア電話に関連付けられた連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使用する場合は、まず、従来の共通エリア電話に関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。
  
### <a name="migrate-common-area-phones"></a>共通領域電話の移行

1. Skype for Business Server 2019 フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。
    
2. コマンドラインで、次のように入力します。
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されたことを確認するには、Skype for Business Server 管理シェルで次のように入力します。
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。
    

