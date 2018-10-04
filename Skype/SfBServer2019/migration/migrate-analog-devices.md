---
title: アナログ デバイスを移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバーの Skype では、アナログ デバイスのサポートを提供します。 具体的には、サポートされているアナログ デバイスは、アナログ音声電話とアナログ fax 機器です。 ビジネス サーバー環境に、Skype でのアナログ デバイスの使用をサポートするために修飾されたゲートウェイを構成できます。 ビジネス サーバー 2019 のように Skype に移行した後も、アナログ デバイスに関連付けられている連絡先オブジェクトを移行する必要があります。 最初にすべてを取得するためにビジネスのサーバー管理シェルを使用して Skype では、レガシーのアナログ デバイスに関連付けられているオブジェクトに連絡し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。
ms.openlocfilehash: ea100f4e26cc38d5eb30f881de61bf415110ca36
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374851"
---
# <a name="migrate-analog-devices"></a>アナログ デバイスを移行します。

ビジネス サーバーの Skype では、アナログ デバイスのサポートを提供します。 具体的には、サポートされているアナログ デバイスは、アナログ音声電話とアナログ fax 機器です。 ビジネス サーバー環境に、Skype でのアナログ デバイスの使用をサポートするために修飾されたゲートウェイを構成できます。 ビジネス サーバー 2019 のように Skype に移行した後も、アナログ デバイスに関連付けられている連絡先オブジェクトを移行する必要があります。 最初にすべてを取得するためにビジネスのサーバー管理シェルを使用して Skype では、レガシーのアナログ デバイスに関連付けられているオブジェクトに連絡し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。

### <a name="to-migrate-analog-devices"></a>アナログ デバイスを移行するには

1. ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。

2. コマンドラインで、次のように入力します。

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 連絡先のすべてのオブジェクト移動されている、Skype をビジネス サーバー 2019 プールのことを確認します。 コマンドラインで、次のように入力します。

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 連絡先オブジェクトがすべて表示されていることを確認して、Skype のビジネス サーバー 2019 プールに関連付けられています。


