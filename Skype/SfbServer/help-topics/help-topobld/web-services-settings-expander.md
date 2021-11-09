---
title: Web サービス設定エキスパンダー
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: トポロジ ビルダー内から、内部 Web サービスと外部 Web サービスの両方に使用されるポート設定を変更できます。 さらに、ドメイン ネーム システム (DNS) 負荷分散を展開する場合は、トポロジ ビルダーを使用して、プール内のすべてのサーバーの物理 IP アドレスに解決されるプールの完全修飾ドメイン名 (FQDN) を構成できます。
ms.openlocfilehash: 66dc22bed1d8e5e24f5403fec9cfa8c2924c810d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854401"
---
# <a name="web-services-settings-expander"></a>Web サービス設定エキスパンダー
 
トポロジ ビルダー内から、内部 Web サービスと外部 Web サービスの両方に使用されるポート設定を変更できます。 さらに、ドメイン ネーム システム (DNS) 負荷分散を展開する場合は、トポロジ ビルダーを使用して、プール内のすべてのサーバーの物理 IP アドレスに解決されるプールの完全修飾ドメイン名 (FQDN) を構成できます。
  
### <a name="editing-web-services-settings"></a>Web サービス設定の編集

1. 該当する Standard Edition フロントエンド サーバーまたは Enterprise Edition フロントエンド プールを選択し、[**プロパティの編集**] をクリックします。
    
2. [**プロパティの編集**] ダイアログ ボックスで、[**Web サービス**] タブをクリックします。
    
    > [!CAUTION]
    > 複数のフロント エンド プールまたはフロント エンド サーバーがある場合は、外部 Web サービスの FQDN が一意である必要があります。 たとえば、フロントエンド サーバーの外部 Web サービス FQDN を **pool01.contoso.com** として定義する場合、別のフロントエンド プールまたはフロント エンド サーバーに pool01.contoso.com を使用することはできません。 ディレクターも展開する場合、ディレクターまたはディレクター プールに対して定義される外部 Web サービス FQDN は、他のディレクターまたはディレクター プール、およびフロント エンド プールまたはフロント エンド サーバーから一意である必要があります。 内部 Web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンド プール、ディレクター、またはディレクター プールから一意である必要があります。
  
3. Enterprise Edition プールのプロパティを編集する場合は、[**FQDN の上書き**] を選択できます。 このオプションは、ドメイン ネーム システム (DNS) 負荷分散を使用する場合にのみ選択してください。 DNS 負荷分散を使用する場合は、[**FQDN の上書き**] を選択してから、テキスト ボックスにプール内のすべてのサーバーの物理 IP アドレスに解決するそのプールの完全修飾ドメイン名 (FQDN) を入力します。 DNS 負荷分散を使用しない場合、および [**FQDN の上書き**] を選択しない場合は、内部 Web サービスの FQDN を変更できません。 内部 Web サービス FQDN は、内部ユーザーがユーザーに接続するために使用する URL Skype for Business Server。
    
4. オプションとして、[**リッスン ポート**] および [**公開ポート**] に、新しい HTTP、HTTPS、または HTTP と HTTPS の値を入力します。リッスン ポートは、着信側のセッション開始プロトコル (SIP) トラフィックをリッスンするためにインターネット インフォメーション サービス (IIS) で使用されるポートです。公開ポートは、ロード バランサーまたはリバース プロキシ サーバーで構成されるポートで、やはり着信 SIP トラフィックをリッスンするために使用されます。既定では、HTTP リッスン ポートと HTTP 公開ポートの両方がポート 80 に設定されており、対応する HTTPS ポートは両方とも 443 に設定されます。2 つの HTTP 公開ポートの既定値は 8080 で、対応する HTTPS ポートは 4443 に設定されます。
    
5. [**OK**] をクリックします。
    
内部 FQDN またはいずれかのリッスン ポートの割り当てを変更する場合は、変更を有効にするために、プール内のすべてのサーバーでローカル セットアップを再実行する必要があります。
  

