---
title: Skype ルーム システム v2 の回復ツールを使用します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この資料では、Skype ルーム システム v2 は、サポートされている状態にする最新のシステムを使用する回復ツールを使用する方法について説明します。
ms.openlocfilehash: 63deb332a520a0752242140f85f200a160eefe0d
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a>Skype ルーム システム v2 の回復ツールを使用します。
 
この資料では、Skype ルーム システム v2 は、サポートされている状態にする最新のシステムを使用する回復ツールを使用する方法について説明します。 Skype ルーム システム v2 のコンソールに「最新のシステム構成」のエラーが表示されて、このツールを使用します。
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>前提条件

最新[Skype ルーム システム v2 のインストール パッケージ](https://go.microsoft.com/fwlink/?linkid=851168)をダウンロードし、USB メモリ スティックまたはネットワーク共有 Skype ルーム システムのバージョン 2 のデバイスにアクセスできるようにします。

[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)をインストールする必要もあります。

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Windows のバージョンを確認します。 

1. 管理者アカウントへのログイン**の設定 > Windows の設定 > 管理者へのサインイン**Skype ルーム システム v2 デバイスから。 このオプションでは、ログイン画面に表示されます。
2. 既定の管理者、管理者用のアカウントにサインイン中のアカウント`admin`パスワードを使用して`sfb`。
3. [スタート] メニューをクリックして`winver.exe`をクリックして、[検索] ボックスに **コマンドの実行*結果をします。
4. 情報ウィンドウの 2 番目の行で 'バージョン' の後の番号を書き留めます。

>[!NOTE]
>1607 またはそれ以前に、新しいバージョンがある場合次の手順に進む前に<a href="#Windows-up">回復する前に更新プログラムの Windows</a>の手順の<a href="#Perform">リカバリを実行する</a>手順を実行します。 表示されるバージョンが 1607 よりも大きい場合は、手順をのみ<a href="#Perform">実行するリカバリ</a>です。

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>(必要な場合)、回復する前に Windows を更新します。

1. Admin ユーザーとしてログインしたまま、中には、管理者として Powershell プロンプトを起動します。
2. コマンドを実行して`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。
3. Windows Update を実行し、Windows 1709 用の更新プログラムをインストールします。
4. 1709 を更新した後、完全な記号は管理者アカウントにバックアップし、 [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)をインストールします。 リンクから更新プログラムを実行することがありますまたは Windows Update を使用します。
5. 省略可能な手順としては、Windows Update からの追加の更新プログラムをインストールします。

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>リカバリを実行します。

1. Skype ルーム システム v2 デバイスの管理者アカウントにサインインし、管理者特権でコマンド プロンプトを起動します。
2. Skype ルーム システム v2 デバイスからできることを確認するにアクセスするのには、 `RecoveryTool.ps1` 、Skype ルーム システム v2 のインストール パッケージから抽出されたファイルに含まれるファイルです。 必須コンポーネントを準備する際に使用する USB ドライブ、ネットワーク共有上のキットをご覧ください。
3. Powershell.exe コマンドを実行して`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。
4. スクリプトのオプションを選択してメッセージが表示されたら`1:"Repair System"`。
5. 完了すると、Skype ルーム システム v2 のデバイスを再起動します。 もの完全に回復した 2 回目、もう一度自動的に再起動されます。



<a name="See"> </a>  
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。


#### 
[Skype ルーム システムのバージョン 2 のヘルプ](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Skype ルームの管理システム v2](skype-room-systems-v2.md)
