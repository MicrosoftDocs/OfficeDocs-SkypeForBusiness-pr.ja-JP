---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: このEnter-CcUpdateコマンドレットは、Skype for Business クラウド コネクタ エディションをメンテナンス モードにすることで、更新プロセスのホスト サーバーを準備します。 アプライアンスは、すべてのサービスを直ちに停止し、継続的な通話を終了し、新しい通話を拒否します。
ms.openlocfilehash: 75be5933e31f3966ab36f9957b78cd89c21a4a31df23b5761000a6e96cd9806e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303650"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

このEnter-CcUpdateコマンドレットは、Skype for Business クラウド コネクタ エディションをメンテナンス モードにすることで、更新プロセスのホスト サーバーを準備します。 アプライアンスは、すべてのサービスを直ちに停止し、継続的な通話を終了し、新しい通話を拒否します。
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、メンテナンス モードに入って更新プロセスのアプライアンスを準備します。
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このEnter-CcUpdateは、進行中の通話を終了するサービスを直ちに停止し、アプライアンスは新しい通話を拒否します。これは他の実稼働アプライアンスに転送されます。 残りの実稼働アプライアンスが、更新の準備中のアプライアンスからの呼び出しを処理するのに十分な容量を持っている必要があります。
  
メンテナンス モードは、アプライアンスで自動更新が有効になっている場合 、たとえば Microsoft が重要な修正プログラムをリリースする場合に便利です。 メンテナンス モードは、自動更新をオフにしたが、一貫して手動更新を実行する場合にも役立ちます。
  
更新プログラムをインストールした後、このコマンドレットを実行して、アプライアンスを実稼働モードExit-CcUpdateできます。
  
> [!NOTE]
> クラウド コネクタ アプライアンスを手動で更新する場合は、Microsoft が次のバージョンをリリースした後、60 日以内に更新する必要があります。 Microsoft は、新しいバージョンのリリース後 60 日間、以前にリリースされたバージョンのクラウド コネクタをサポートしています。 
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このEnter-CCUpdateは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし 
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

