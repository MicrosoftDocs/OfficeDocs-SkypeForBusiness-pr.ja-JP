---
title: 共通領域電話の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 共通領域電話は、IP 電話のほとんどは、共有ワークスペース、または共通の領域で多くの場合にあるロビー、キッチン、または工場出荷時のフロアのようです。 共通領域電話は、Skype のビジネス サーバーのユニファイド コミュニケーション (UC) の機能を提供するコンピューターに接続する必要はありません。 ビジネス サーバー 2019 用に展開を Skype に移行した後も従来の共通領域電話に関連付けられている連絡先オブジェクトを移行する必要があります。 ビジネス サーバー管理シェルの Skype を使用する従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。
ms.openlocfilehash: d17e15224a9124eaf3e9fd6696e6ecd9265044eb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231666"
---
# <a name="migrate-common-area-phones"></a>共通領域電話の移行

共通領域電話は、IP 電話のほとんどは、共有ワークスペース、または共通の領域で多くの場合にあるロビー、キッチン、または工場出荷時のフロアのようです。 共通領域電話は、Skype のビジネス サーバーのユニファイド コミュニケーション (UC) の機能を提供するコンピューターに接続する必要はありません。 ビジネス サーバー 2019 用に展開を Skype に移行した後も従来の共通領域電話に関連付けられている連絡先オブジェクトを移行する必要があります。 Skype ビジネス サーバー管理シェルを使用すると、従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。
  
### <a name="migrate-common-area-phones"></a>共通領域電話の移行

1. ビジネス サーバー 2019 のフロント エンド サーバーの Skype、Skype ビジネス サーバー管理シェルを開きます。
    
2. コマンド ・ ラインから次のように入力します。
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. 連絡先のすべてのオブジェクト移動されている、Skype をビジネス サーバー 2019 プールのことを確認するには、ビジネスのサーバー管理シェルの Skype から次のとおり入力します。
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    連絡先オブジェクトがすべて表示されていることを確認して、Skype のビジネス サーバー 2019 プールに関連付けられています。
    

