---
title: コール パーク アプリケーション設定の移行
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
description: コールパークアプリケーションの移行には、Skype for Business Server 2019 プールを、従来のインストールでアップロードされたカスタム音楽保留ファイルと共にプロビジョニングすること、およびサービスレベル設定を復元して、Skype for Business Server 2019 プールへのすべてのコールパークオービットを retargeting することが含まれます。 カスタマイズした保留音のファイルがプールに構成されている場合は、これらのファイルを新しい Skype for Business Server 2019 プールにコピーする必要があります。 また、コールパーク用にアップロードされたカスタマイズされた保留音ファイルのバックアップコピーを別に保持するために、コールパークのカスタマイズされた保留音のファイルを別の場所にバックアップすることをお勧めします。 コール パーク アプリケーションのカスタマイズされた保留音ファイルは、プールのファイル ストアに格納されています。 オーディオファイルをプールファイルストアから Skype for Business Server 2019 ファイルストアにコピーするには、Xcopy コマンドを次のパラメーターと共に使用します。
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752819"
---
# <a name="migrate-call-park-application-settings"></a>コール パーク アプリケーション設定の移行

コールパークアプリケーションの移行には、Skype for Business Server 2019 プールを、従来のインストールにアップロードされた任意のカスタムの保留中ファイルと共にプロビジョニングすること、サービスレベルの設定を復元すること、およびすべてのコールパークオービットを Skype for Business Server 2019 プールに再作成することが含まれます。 カスタマイズした保留音のファイルがプールに構成されている場合は、これらのファイルを新しい Skype for Business Server 2019 プールにコピーする必要があります。 また、コールパーク用にアップロードされたカスタマイズされた保留音ファイルのバックアップコピーを別に保存するために、コールパークのカスタマイズされた保留音ファイルをバックアップすることをお勧めします。 コール パーク アプリケーションのカスタマイズされた保留音ファイルは、プールのファイル ストアに格納されています。 オーディオファイルをプールファイルストアから Skype for Business Server 2019 ファイルストアにコピーするには、 **Xcopy**コマンドを次のパラメーターと共に使用します。 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

カスタマイズしたすべてのオーディオファイルが Skype for business Server 2019 ファイルストアにコピーされている場合、Skype for Business Server 2019 プールのコールパークアプリケーション設定を構成する必要があります。また、従来のプールに関連付けられているコールパークオービット範囲は、Skype for Business Server の2019プールに再割り当てする必要があります。

コールパークアプリケーションの設定には、ピックアップタイムアウトのしきい値、保留音の保留を有効または無効にするか、最大通話ピックアップ試行回数、およびタイムアウト要求が含まれます。 **New-cscpsconfiguration**コマンドレットを実行するには、Skype For Business Server 管理シェルを使用してコールパークアプリケーションの設定を管理する必要があります。 Skype for Business Server コントロールパネルを使用してコールパークアプリケーションの設定を管理することはできません。 

## <a name="reconfigure-the-call-park-service-settings"></a>Call Park Service の設定を再構成する

1. Skype for Business Server 2019 フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。

2. コマンドラインで、次のように入力します。

    > [!NOTE]
    > Skype for Business Server 2019 コールパークアプリケーションの設定が従来の設定と同じ場合は、この手順を省略できます。 コールパークアプリケーションの設定が Skype for Business Server 2019 と従来の環境で異なる場合は、次のコマンドレットをテンプレートとして使用して、それらの変更を更新します。 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

すべてのコールパークオービット範囲を従来のプールから Skype for Business Server 2019 プールに再割り当てするには、Skype for Business Server コントロールパネルまたは Skype for business Server 管理シェルのいずれかを使用できます。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してすべてのコールパークオービット範囲を再割り当てする

1. Skype for Business Server コントロールパネルを開きます。

2. 左側のウィンドウで、[**音声機能**] を選択します。

3. [**コール パーク**] タブを選択します。 

4. 従来のプールに割り当てられているコールパークオービット範囲のそれぞれについて、[**宛先サーバーの FQDN** ] 設定を編集し、コールパーク要求を処理する Skype For business server 2019 プールを選択します。 

5. [**コミット**] を選択して変更を保存します。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してすべてのコールパークオービット範囲を再割り当てする

1. Skype for Business Server 管理シェルを開きます。

2. コマンド ラインで、次のように入力します。

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    このコマンドレットを実行すると、展開内のコール パーク オービットの範囲がすべて表示されます。 **CallParkServiceId**および**Callparkserverfqdn**パラメーターが従来のプールとして設定されているすべてのコールパークオービットを再割り当てする必要があります。 

    従来のコールパークオービット範囲を Skype for Business Server 2019 プールに再割り当てするには、コマンドラインで次のように入力します。

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

すべてのコールパークオービット範囲を Skype for Business Server 2019 プールに再割り当てした後、コールパークアプリケーションの移行プロセスが完了し、Skype for Business Server 2019 プールが、今後のコールパーク要求をすべて処理するようになります。


