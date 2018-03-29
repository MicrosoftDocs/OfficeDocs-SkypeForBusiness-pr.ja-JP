---
title: 入力 CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Enter CcUpdate コマンドレットでは、メンテナンス モードで配置することによって更新プロセスにホスト サーバーでビジネス クラウド コネクタ版 Skype を準備します。 アプライアンスの isdrained-は、既存のすべての呼び出しは完了しますが、新しい呼び出しは拒否されます。
ms.openlocfilehash: ed9f3f614829cd5b6bc2cd5499c6889258d67531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="enter-ccupdate"></a>入力 CcUpdate
 
Enter CcUpdate コマンドレットでは、メンテナンス モードで配置することによって更新プロセスにホスト サーバーでビジネス クラウド コネクタ版 Skype を準備します。 アプライアンスは、「放電」つまり、既存すべて呼び出しは完了しますが、新しい呼び出しは拒否されます。 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、アプライアンスをメンテナンス モードに入れて更新プロセスに備えています。
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

入力 CcUpdate コマンドレットは、クラウド コネクタ アプライアンスを実行中のすべての呼び出しが完了すると、アプライアンスは、他の生産のアプライアンスに転送されるすべての新しい呼び出しが拒否されますがようにします。 このコマンドレットを使用すると、エンド ・ ユーザーの呼び出しに影響を与えずに、アプライアンスを更新できます。 生産の残りのアプライアンスに更新する準備を行うアプライアンスからの呼び出しを処理するために十分な容量があることを確認する必要があります。
  
お使いのアプライアンスで自動更新が有効になっている場合に、マイクロソフトが重要な修正プログラムをリリースするときなどで、メンテナンス モードは役に立ちます。メンテナンス モードは、自動更新をオフにすることを決めた上で、一貫して手動での更新を実行するという場合にも役立ちます。
  
更新プログラムのインストール後、Exit-CcUpdate コマンドレットを実行することによってアプライアンスを実稼働モードに戻すことができます。
  
> [!NOTE]
> クラウド コネクタ アプライアンスを手動で更新する場合は、次のバージョンをリリースした後、60 日以内に更新する必要があります。 マイクロソフトは、新しいバージョンがリリースされた後、60 日間、過去にリリースされたバージョンのクラウドのコネクタをサポートしています 
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Enter-CCUpdate コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし 
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[終了 CcUpdate](exit-ccupdate.md)
  

