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
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: 入力-CcUpdate コマンドレットは、Skype for Business Cloud Connector Edition host server をメンテナンスモードにして、更新プロセスを準備します。 アプライアンスは直ちにすべてのサービスを停止して、進行中の通話を終了し、新しい通話を拒否します。
ms.openlocfilehash: 694faf7f03fb672ec61ee97db08fb61bcf0dc532
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003457"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

入力-CcUpdate コマンドレットは、Skype for Business Cloud Connector Edition host server をメンテナンスモードにして、更新プロセスを準備します。 アプライアンスは直ちにすべてのサービスを停止して、進行中の通話を終了し、新しい通話を拒否します。
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、アプライアンスをメンテナンス モードに入れて更新プロセスに備えています。
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

入力-CcUpdate コマンドレットは、現在進行中の通話を終了するすべてのサービスを直ちに停止します。このアプライアンスは、他の運用アプライアンスに転送される新しい通話を拒否します。 更新を準備しているアプライアンスからの通話を処理するために、残りの本番アプライアンスに十分な容量があることを確認する必要があります。
  
お使いのアプライアンスで自動更新が有効になっている場合に、マイクロソフトが重要な修正プログラムをリリースするときなどで、メンテナンス モードは役に立ちます。メンテナンス モードは、自動更新をオフにすることを決めた上で、一貫して手動での更新を実行するという場合にも役立ちます。
  
更新プログラムをインストールした後、終了-CcUpdate コマンドレットを実行して、アプライアンスを運用モードに戻すことができます。
  
> [!NOTE]
> クラウドコネクタのアプライアンスを手動で更新する場合は、Microsoft が次のバージョンをリリースしてから60日以内に更新する必要があります。 Microsoft は、新しいバージョンがリリースされてから60日間、以前リリースされたクラウドコネクタのバージョンをサポートしています。 
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Enter-CCUpdate コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし 
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

