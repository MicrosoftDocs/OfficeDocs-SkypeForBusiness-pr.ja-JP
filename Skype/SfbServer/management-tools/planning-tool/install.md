---
title: Skype for Business Server 2015 に計画ツールをインストールする
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
description: Skype for Business Server 2015 計画ツールを使用して Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。 計画ツールは、Skype for Business Server 2015 をインストールする予定のドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要があります。 計画ツールに関連する Readme ファイルは、ツールのインストールと使用に関する重要な情報を詳細に示します。 わかりやすくするために、Readme ファイルの情報の一部をここに転載します。
ms.openlocfilehash: 29a3bd35191cf326cafd1f4ad4f14fab50e47ea3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122381"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 に計画ツールをインストールする

Skype for Business Server 2015 計画ツールを使用して Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。 計画ツールは、Skype for Business Server 2015 をインストールする予定のドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要があります。 計画ツールに関連する Readme ファイルは、ツールのインストールと使用に関する重要な情報を詳細に示します。 わかりやすくするために、Readme ファイルの情報の一部をここに転載します。

> [!IMPORTANT]
> 計画ツールでは、ツールをインストールするコンピューターに対する管理者権限とアクセス許可を持つユーザーによるインストールが必要です。

計画ツールのインストールと操作でサポートされているオペレーティング システムは次のとおりです。

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7、32 ビット版

- Windows 7、64 ビット版、Windows on Win32 (WOW) 使用

- Windows Server 2008 R2、WOW 使用

さらに、計画ツールには、Microsoft .NET Framework 4.5 が必要です。

プレインストール要件が満たされた後、計画ツールをインストールできます。



## <a name="to-install-the-planning-tool"></a>計画ツールをインストールするには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2. Windows エクスプローラーまたはコマンド ウィンドウを使用して、計画ツールのインストール ファイルをダウンロードしたディレクトリを探します。

3. 次のSkypeForBusinessPlanningTool.msi。 Windows Explorer で、ファイルをダブルクリックします。 コマンド ウィンドウで、ファイルの名前を入力し **、Enter** キーを押してファイルを実行します。

4. Skype for Business **Server 2015** の [ようこそ] ページの [計画ツールのセットアップ ウィザード] で、[次へ] を **クリックします**。

5. **[使用許諾契約書]** を読んでから、使用許諾契約書に同意する場合には **[使用許諾契約書に同意します]** チェック ボックスをオンにして、**[次へ]** をクリックします。

6. 計画ツール ファイルをインストールする場所を選択します。 既定の場所は C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool です。 インストール先を変更するには、**[変更]** をクリックします。 **[インストール先フォルダの変更]** で、ファイルをインストールする場所を参照または入力し、**[OK]** をクリックしてから、**[次へ]** をクリックします。

7. これで、インストーラーは計画ツールをインストールする準備ができました。 **[インストール]** をクリックして、インストール プロセスを開始します。

8. インストールが開始され、進行状況が表示されます。 インストールが正常に完了したら、**[完了]** をクリックします。

9. 計画ツールを使用する準備ができました。

## <a name="optional-software"></a>オプション ソフトウェア
<a name="Optional_Software"> </a>

Skype for Business Server 2015 計画ツールは、Microsoft Excel と Microsoft Visio にエクスポートするように設計されています。 これらのアプリケーションは計画ツールの操作には必要ありませんが、設計の展開とドキュメントに大きな価値を追加します。

### <a name="microsoft-excel"></a>Microsoft Excel

デザインを Microsoft Excel にエクスポートすると、スプレッドシートに 7 つのタブが表示されるレポートが作成されます。

- 概要 - ユーザー数、容量設定、サーバー プロファイル情報など、サイト構成に関する情報を表示します。

- ハードウェア プロファイル - CPU、メモリ、ディスク、ネットワーク インターフェイスなど、トポロジで指定されたサーバーの推奨ハードウェア構成に関するレポートを表示します。 サーバー コンポーネントの数量と推奨仕様も含まれています。 さらに、各サーバーはサイトによって定義され、サイトごとにサーバー要件を完全に表します。

- ポート要件 - 有効になっているすべてのポートのレポートと、ドメイン ネーム システム負荷分散 (DNS LB) とハードウェア ロード バランサー (HLB) との関連付けを表示します。 このレポートを使用して、ファイアウォールと DNS LB および HLB 構成を計画する必要があります。

- 概要レポート - エッジ サーバー ネットワークのセットアップに必要な設定の概要を表示します。

- 証明書レポート - エッジ サーバーを実行するために必要な証明書に必要なサブジェクト名とサブジェクト代替名を表示します。

- ファイアウォール レポート - 外部インターフェイスと内部インターフェイスの両方の送信元ポートと宛先ポートと IP アドレスを表示します。

- DNS レポート - 作成する各 DNS エントリに必要な完全修飾ドメイン名 (FQDN) と IP/VIP アドレスを表示します。

### <a name="microsoft-visio"></a>Microsoft Visio

設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。

> [!NOTE]
> デザインが 3 台を超えるフロントエンド サーバーを必要とする十分な大きい場合は、フロントエンド プール、フロントエンド サーバー、SQL Server、IP アドレス、および FQDN を実行しているコンピューターに対して追加のページが作成されます。

- グローバル トポロジ - 構成済みの Skype for Business Server 2015 サイトの図。

- [サイト名] タブ - エッジ サーバー、ファイアウォール、ゲートウェイを備えた公衆交換電話網 (PSTN)、および内部サーバーの展開を含むサイト構成トポロジを表示します。 内部展開は、フロントエンド プール、SQL Server ベースのサーバー、Active Directory ドメイン サービス、ディレクター、Exchange ユニファイド メッセージング (UM) サーバー、Exchange メールボックス サーバー、Office Web Apps サーバー、仲介サーバー、常設チャット サーバーなど、構成済みのサーバーとプールで構成されます。

- エッジ ネットワークダイアグラム - 関連付けられた IP アドレスと FQDN を含むエッジ サーバー構成の詳細を示す図。 DNS 負荷分散とハードウェア ロード バランサーも含まれています。 さらに、ディレクターとフロント エンド サーバーまたはフロント エンド プールが表示され、関連付けられた DNS LB または HLB と割り当てられた IP アドレス (計画ツールは IPv4 アドレスと IPv6 アドレスの両方をサポート) と FQDN が表示されます。

## <a name="see-also"></a>関連項目
<a name="Optional_Software"> </a>

[計画ツールのインストール](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)