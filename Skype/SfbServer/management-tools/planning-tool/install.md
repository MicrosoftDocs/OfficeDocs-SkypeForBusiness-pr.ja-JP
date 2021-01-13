---
title: Skype for Business Server 2015 での計画ツールのインストール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Skype for Business Server 2015 計画ツールを使用して Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。 計画ツールは、Skype for Business Server 2015 をインストールする予定のドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要があります。 計画ツールに関連する Readme ファイルでは、ツールのインストールと使用に関する重要な情報が詳細に示されます。 わかりやすくするために、Readme ファイルの情報の一部をここに転載します。
ms.openlocfilehash: 902249e042694a37594c6dc0b753b0c1388c0729
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834727"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での計画ツールのインストール

Skype for Business Server 2015 計画ツールを使用して Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。 計画ツールは、Skype for Business Server 2015 をインストールする予定のドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要があります。 計画ツールに関連する Readme ファイルには、ツールのインストールと使用に関する重要な情報が詳細に示されています。 わかりやすくするために、Readme ファイルの情報の一部をここに転載します。

> [!IMPORTANT]
> 計画ツールを使用するには、ツールをインストールするコンピューターに管理者権限とアクセス許可を持つユーザーがインストールする必要があります。

計画ツールのインストールと操作でサポートされているオペレーティング システムは次のとおりです。

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7、32 ビット版

- Windows 7、64 ビット版、Windows on Win32 (WOW) 使用

- Windows Server 2008 R2、WOW 使用

さらに、計画ツールには Microsoft .NET Framework 4.5 が必要です。

プレインストール要件が満たされた後、計画ツールをインストールできます。



## <a name="to-install-the-planning-tool"></a>計画ツールをインストールするには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2. エクスプローラーまたはコマンド ウィンドウを使用して、計画ツールのインストール ファイルをダウンロードしたディレクトリを探します。

3. 次のSkypeForBusinessPlanningTool.msi。 Windows Explorer で、ファイルをダブルクリックします。 コマンド ウィンドウで、ファイルの名前を入力し **、Enter** キーを押してファイルを実行します。

4. Skype for Business **Server 2015** の計画ツールセットアップ ウィザードの [ようこそ] ページで、[次へ] をクリック **します**。

5. **[使用許諾契約書]** を読んでから、使用許諾契約書に同意する場合には **[使用許諾契約書に同意します]** チェック ボックスをオンにして、**[次へ]** をクリックします。

6. 計画ツール ファイルをインストールする場所を選択します。 既定の場所は C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool です。 インストール先を変更するには、**[変更]** をクリックします。 **[インストール先フォルダの変更]** で、ファイルをインストールする場所を参照または入力し、**[OK]** をクリックしてから、**[次へ]** をクリックします。

7. これで、インストーラーは計画ツールをインストールする準備ができました。 **[インストール]** をクリックして、インストール プロセスを開始します。

8. インストールが開始され、進行状況が表示されます。 インストールが正常に完了したら、**[完了]** をクリックします。

9. 計画ツールを使用する準備ができました。

## <a name="optional-software"></a>オプション ソフトウェア
<a name="Optional_Software"> </a>

Skype for Business Server 2015 計画ツールは、Microsoft Excel および Microsoft Visio にエクスポートするように設計されています。 これらのアプリケーションは計画ツールの操作には必要ありませんが、設計の展開とドキュメントに大きな価値を加える必要があります。

### <a name="microsoft-excel"></a>Microsoft Excel

デザインを Microsoft Excel にエクスポートすると、スプレッドシートに 7 つのタブを表示するレポートが作成されます。

- 概要 - ユーザー数、容量設定、サーバー プロファイル情報など、サイト構成に関する情報を表示します。

- ハードウェア プロファイル - CPU、メモリ、ディスク、ネットワーク インターフェイスなど、トポロジで指定されているサーバーの推奨ハードウェア構成に関するレポートを表示します。 サーバー コンポーネントの数量と推奨仕様も含まれています。 また、各サーバーはサイトごとに定義され、サイトごとにサーバーの要件を完全に表します。

- ポートの要件 - 有効になっているすべてのポートと、ドメイン ネーム システム負荷分散 (DNS LB) およびハードウェア ロード バランサー (HLB) との関連付けに関するレポートを表示します。 このレポートを使用して、ファイアウォールと DNS LB および HLB 構成を計画する必要があります。

- 概要レポート - エッジ サーバー ネットワークのセットアップに必要な設定の概要が表示されます。

- 証明書レポート - エッジ サーバーを実行するために必要な証明書に必要なサブジェクト名とサブジェクト代替名を表示します。

- ファイアウォール レポート - 外部インターフェイスと内部インターフェイスの両方の送信元ポートと宛先ポートおよび IP アドレスを表示します。

- DNS レポート - 作成する各 DNS エントリに必要な完全修飾ドメイン名 (FQDN) と IP/VIP アドレスを表示します。

### <a name="microsoft-visio"></a>Microsoft Visio

設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。

> [!NOTE]
> 設計が 3 台を超えるフロントエンド サーバーを必要とする大きい場合は、フロントエンド プール、フロントエンド サーバー、SQL Server、IP アドレス、および FQDN を実行しているコンピューターに対して追加のページが作成されます。

- グローバル トポロジ - 構成済みの Skype for Business Server 2015 サイトの図。

- [サイト名] タブ - エッジ サーバー、ファイアウォール、ゲートウェイ付き公衆交換電話網 (PSTN)、および内部サーバーの展開を使用したサイト構成トポロジを表示します。 内部展開は、フロントエンド プール、SQL Server ベースのサーバー、Active Directory ドメイン サービス、ディレクター、Exchange ユニファイド メッセージング (UM) サーバー、Exchange メールボックス サーバー、Office Web Apps サーバー、仲介サーバー、常設チャット サーバーなど、構成済みのサーバーとプールで構成されます。

- エッジ ネットワークダイアグラム - 関連付けられた IP アドレスと FQDN を使用したエッジ サーバー構成の詳細を示す図。 DNS 負荷分散とハードウェア ロード バランサーも含まれています。 さらに、ディレクターとフロントエンド サーバーまたはフロントエンド プールが表示され、関連付けられた DNS LB または HLB と、割り当てられた IP アドレス (計画ツールは IPv4 アドレスと IPv6 アドレスの両方をサポートしています) と FQDN が表示されます。

## <a name="see-also"></a>関連項目
<a name="Optional_Software"> </a>

[計画ツールのインストール](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
