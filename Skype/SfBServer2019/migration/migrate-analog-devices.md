---
title: アナログ デバイスの移行
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
description: Skype for Business Serverアナログ デバイスのサポートを提供します。 具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。 アプリケーション環境でのアナログ デバイスの使用をサポートするために、修飾されたゲートウェイSkype for Business Serverできます。 2019 Skype for Business Server後、アナログ デバイスに関連付けられている連絡先オブジェクトも移行する必要があります。 従来Skype for Business Server Skype for Business Serverに関連付けられているすべての連絡先オブジェクトを取得し、それらのオブジェクトを 2019 プールに移動するには、Skype for Business Server 管理シェルを使用します。
ms.openlocfilehash: d64552a53b5cb37187a25febe5ce6171d1c64ec9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599692"
---
# <a name="migrate-analog-devices"></a>アナログ デバイスの移行

Skype for Business Serverアナログ デバイスのサポートを提供します。 具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。 アプリケーション環境でのアナログ デバイスの使用をサポートするために、修飾されたゲートウェイSkype for Business Serverできます。 2019 Skype for Business Server後、アナログ デバイスに関連付けられている連絡先オブジェクトも移行する必要があります。 従来Skype for Business Server Skype for Business Serverに関連付けられているすべての連絡先オブジェクトを取得し、それらのオブジェクトを 2019 プールに移動するには、Skype for Business Server 管理シェルを使用します。

### <a name="to-migrate-analog-devices"></a>アナログ デバイスを移行するには

1. 管理シェルをSkype for Business Serverする: [スタート] をクリックし、[すべてのプログラム] をクリックし、[Microsoft Skype for Business Server **2019]** をクリックし、[管理シェルSkype for Business Server **クリックします**。

2. コマンドラインで、次のように入力します。

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. すべての連絡先オブジェクトが 2019 プールに移動Skype for Business Server確認します。 コマンドラインで、次のように入力します。

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. すべての連絡先オブジェクトが 2019 プールに関連付Skype for Business Server確認します。


