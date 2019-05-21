---
title: Skype for Business Server 2015 の計画ツールのインストール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Skype for business Server 2015 計画ツールを使用して、Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。 計画ツールは、Skype for Business Server 2015 のインストールを計画しているドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要はありません。 計画ツールに付随する Readme ファイルには、ツールのインストールと使用に関する重要な情報が説明されています。 わかりやすくするために、Readme ファイルの情報の一部をここに転載します。
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279128"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の計画ツールのインストール

Skype for business Server 2015 計画ツールを使用して、Skype for Business Server 2015 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。 計画ツールは、Skype for Business Server 2015 のインストールを計画しているドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要はありません。 計画ツールに付随する Readme ファイルには、ツールのインストールと使用に関する重要な情報が説明されています。 わかりやすくするために、Readme ファイルの情報の一部をここに転載します。

> [!IMPORTANT]
> 計画ツールをインストールするには、ツールをインストールするコンピューターの管理者権限と権限を持つユーザーによるインストールが必要です。

計画ツールのインストールと運用でサポートされているオペレーティングシステムは次のとおりです。

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7、32 ビット版

- Windows 7、64 ビット版、Windows on Win32 (WOW) 使用

- Windows Server 2008 R2、WOW 使用

さらに、計画ツールには Microsoft .NET Framework 4.5 が必要です。

プレインストールの要件が満たされたら、計画ツールをインストールすることができます。



## <a name="to-install-the-planning-tool"></a>計画ツールをインストールするには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2. Windows エクスプローラーまたはコマンドウィンドウを使って、計画ツールのインストールファイルをダウンロードしたディレクトリを見つけます。

3. SkypeForBusinessPlanningTool.msi を検索します。Windows Explorer で、ファイルをダブルクリックします。コマンド ウィンドウで、ファイル名を入力してから、**Enter** キーを押してファイルを実行します。

4. **Skype for Business Server 2015、計画ツール セットアップ ウィザード  ** の [ようこそ] ページで、[**次へ**] をクリックします。

5. [**使用許諾契約書**] を読んでから、使用許諾契約書に同意する場合には [**使用許諾契約書に同意します**] チェック ボックスをオンにして、[**次へ**] をクリックします。

6. 計画ツール ファイルをインストールする場所を選択します。既定の場所は C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool です。インストール先を変更するには、[**変更 **] をクリックします。[**インストール先フォルダーの変更**] で、ファイルをインストールする場所を参照または入力し、[**OK **] をクリックしてから、[**次へ**] をクリックします。

7. これで、インストーラーで計画ツールをインストールする準備が整いました。 [**インストール**] をクリックして、インストール プロセスを開始します。

8. インストールが開始され、進行状況が表示されます。 インストールが正常に完了したら、[**完了**] をクリックします。

9. 計画ツールを使用する準備ができました。

## <a name="optional-software"></a>オプション ソフトウェア
<a name="Optional_Software"> </a>

Skype for Business Server 2015 計画ツールは、Microsoft Excel と Microsoft Visio にエクスポートするように設計されています。 これらのアプリケーションは計画ツールの操作には必要ありませんが、設計の展開とドキュメントに大きな価値を加えることになります。

### <a name="microsoft-excel"></a>Microsoft Excel

デザインを Microsoft Excel にエクスポートすると、次の 7 つのタブがあるスプレッドシートを表示するレポートが作成されます。

- サマリー: ユーザー数、容量の設定、サーバーのプロファイル情報など、サイトの構成に関する情報を表示します。

- ハードウェアプロファイル-CPU、メモリ、ディスク、ネットワークインターフェイスなど、トポロジで指定されているサーバーの推奨ハードウェア構成に関するレポートを表示します。 サーバー コンポーネントの数量および推奨仕様も含まれます。 各サーバーはサイト別に定義されているので、サイトごとのサーバー要件を詳細に示します。

- [ポート要件]-有効になっているすべてのポートのレポートと、ドメイン名システム負荷分散 (DNS LB) とハードウェアロードバランサー (HLB) との関連付けが表示されます。 このレポートは、ファイアウォール、DNS LB、および HLB の構成を計画するために使用します。

- サマリーレポート-エッジサーバーネットワークのセットアップに必要な設定の一般的な概要が表示されます。

- 証明書レポート-エッジサーバーを実行するために必要な証明書に必要なサブジェクト名とサブジェクトの代替名が表示されます。

- [ファイアウォールレポート]-外部インターフェイスと内部インターフェイスの両方について、ソースと宛先のポートと IP アドレスが表示されます。

- DNS レポート-作成する各 DNS エントリに必要な完全修飾ドメイン名 (FQDN) と IP/VIP アドレスが表示されます。

### <a name="microsoft-visio"></a>Microsoft Visio

設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。

> [!NOTE]
> 3台以上のフロントエンドサーバーが必要な設計の場合は、フロントエンドプール、フロントエンドサーバー、SQL Server を実行しているコンピューター、IP アドレス、Fqdn の追加ページが作成されます。

- グローバルトポロジ-構成済みの Skype for Business Server 2015 サイトの図。

- [サイト名] タブ-microsoft Edge Server、ファイアウォール、公衆交換電話網 (PSTN)、および内部サーバー展開と共に、サイトの構成トポロジが表示されます。 内部展開は、フロントエンドプール、SQL Server ベースのサーバー、Active Directory ドメインサービス、ディレクター、Exchange ユニファイドメッセージング (UM) サーバー、Exchange メールボックスサーバー、Office Web Apps サーバーなど、構成済みのサーバーとプールで構成されます。仲介サーバーと常設チャットサーバー。

- エッジネットワーク図-関連する IP アドレスと Fqdn を含むエッジサーバー構成の詳細を示す図。 DNS 負荷分散やロード バランサー機器も含まれます。 さらに、関連付けられた DNS LB または HLB および割り当てられた IP アドレス (計画ツールが IPv4 アドレスと IPv6 アドレスの両方をサポートします) と FQDN が表示されたディレクターとフロントエンドサーバーまたはフロントエンドプールが表示されます。

## <a name="see-also"></a>関連項目
<a name="Optional_Software"> </a>

[Installing the Planning Tool](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
