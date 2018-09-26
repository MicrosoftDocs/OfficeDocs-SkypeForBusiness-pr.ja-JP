---
title: 共通領域電話を移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 共通領域電話は、IP 電話のほとんどは、共有ワークスペース、または共通の領域で多くの場合にあるロビー、キッチン、または工場出荷時のフロアのようです。 共通領域電話は、Skype のビジネス サーバーのユニファイド コミュニケーション (UC) の機能を提供するコンピューターに接続する必要はありません。 ビジネス サーバー 2019 用に展開を Skype に移行した後も従来の共通領域電話に関連付けられている連絡先オブジェクトを移行する必要があります。 ビジネス サーバー管理シェルの Skype を使用する従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。
ms.openlocfilehash: 6d5adebd4ab1b4cb79d79f4049c7d7456bb07a29
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028027"
---
# <a name="migrate-common-area-phones"></a>共通領域電話を移行します。

共通領域電話は、IP 電話のほとんどは、共有ワークスペース、または共通の領域で多くの場合にあるロビー、キッチン、または工場出荷時のフロアのようです。 共通領域電話は、Skype のビジネス サーバーのユニファイド コミュニケーション (UC) の機能を提供するコンピューターに接続する必要はありません。 ビジネス サーバー 2019 用に展開を Skype に移行した後も従来の共通領域電話に関連付けられている連絡先オブジェクトを移行する必要があります。 Skype ビジネス サーバー管理シェルを使用すると、従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。
  
### <a name="migrate-common-area-phones"></a>共通領域電話を移行します。

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
    

