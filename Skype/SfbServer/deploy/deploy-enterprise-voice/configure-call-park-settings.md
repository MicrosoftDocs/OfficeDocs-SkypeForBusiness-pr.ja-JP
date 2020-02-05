---
title: Skype for Business のコールパーク設定を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Skype for Business Server Enterprise Voice でのコールパーク設定を変更します。
ms.openlocfilehash: e9410d3b088e5978588de991aeaa9da73327f50a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768130"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Skype for Business のコールパーク設定を構成する

Skype for Business Server Enterprise Voice でのコールパーク設定を変更します。

既定のコールパーク設定を使用しない場合は、カスタマイズすることができます。 コールパークアプリケーションをインストールすると、既定でグローバル設定が構成されます。 グローバル設定を変更できます。また、サイト固有の設定を指定することもできます。 新しいサイト固有の設定を作成するには、 **CsCpsConfiguration**コマンドレットを使用します。 既存の設定を変更するには、 **CsCpsConfiguration**コマンドレットを使用します。

> [!NOTE]
> 少なくとも、保留された通話が時間切れになりリングバックが失敗した場合に使用する代替宛先の [**OnTimeoutURI**] オプションは構成することをお勧めします。

**New-CsCpsConfiguration** コマンドレットまたは **Set-CsCpsConfiguration** コマンドレットを使用して、次のいずれかの設定を構成します。


| **このオプション:**                     | **指定する内容:**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | 通話が保留されてから、呼び出しに応答した電話にかけ直されるまでの経過時間。  <br/> この値は、hh:mm:ss の形式で入力し、時間、分、および秒を指定する必要があります。最小値は 10 秒、最大値は 10 分です。既定値は 00:01:30 です。  <br/> |
| **EnableMusicOnHold** <br/>          | 通話が保留されている間、発信者に対して音楽を再生するかどうか。  <br/> 値は True または False です。既定値は True です。  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | 保留された通話が [**OnTimeoutURI**] で指定した代替 URI (Uniform Resource Identifier) に転送される前に、応答電話にかけ直される回数。既定値は 1 です。<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | **MaxCallPickupAttempts** を超過した場合に、応答のない保留通話のルーティング先となるユーザーまたは応答グループの SIP アドレス。 <br/> 値は、文字列 sip: で始まる SIP URI にする必要があります。たとえば、sip:bob@contoso.com などです。既定値は転送アドレスではありません。<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>コールパークの設定を構成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. 次のコマンドレットを実行します。

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > サイトを識別するには、**Get-CsSite** コマンドレットを使用します。 詳細については、「Skype for Business Server 管理シェルのドキュメント」を参照してください。

    次に例を示します。

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>関連項目

[Skype for Business 2015 でのコール パーク保留音のカスタマイズ](customize-call-park-music-on-hold.md)

[新規-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
