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
localization_priority: Normal
description: Skype for Business Serverアナログ デバイスのサポートを提供します。 具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。 アプリケーション環境でのアナログ デバイスの使用をサポートするために、修飾されたゲートウェイSkype for Business Serverできます。 2019 Skype for Business Server後、アナログ デバイスに関連付けられている連絡先オブジェクトも移行する必要があります。 従来Skype for Business Server Skype for Business Serverに関連付けられているすべての連絡先オブジェクトを取得し、それらのオブジェクトを 2019 プールに移動するには、Skype for Business Server 管理シェルを使用します。
ms.openlocfilehash: 464531fcffbe251d6a0868e86b1b9edccc898fdeeb0963ed0f10c2b653dfe93b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337267"
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


