---
title: 組織の更新 アプリを管理する
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: how-to
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
description: 組織内のユーザー向けに Teams で更新 アプリを管理する方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 214ae4f925f3a33e82fb4eac8186f02e0a65cbc2
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784422"
---
# <a name="manage-the-updates-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織の更新 アプリを管理する

## <a name="what-is-the-updates-app"></a>更新 アプリとは

Microsoft Teams アプリの更新は、組織のメンバーが更新プログラムを作成、確認、送信するための一元的な場所を提供します。 テンプレートを作成すると、更新 アプリを使用して、組織で必要なものを追跡できます。 更新は、デスクトップとモバイルの両方で使用できます。

Teams では、ユーザーは Teams アプリ ストアから更新を取得できます。 [ **送信]** ページに送信する必要があるすべての更新プログラムが表示されます。 更新を快適に使用できるように[、更新記事の概要に](https://support.microsoft.com/office/get-started-in-updates-c03a079e-e660-42dc-817b-ca4cfd602e5a)関する記事をユーザーと共有できます。

[![Teams for desktop の [送信] ページの画像。](media/updates-submit-small.png)](media/updates-submit.png#lightbox)

ユーザーは、[ **レビュー** ] ページで割り当てた更新プログラムを表示できます。

[![Teams for desktop の [レビュー] ページの画像。](media/updates-home-small.png)](media/updates-home.png#lightbox)

ユーザーに更新プログラムが割り当てられると、そのユーザーの Teams アクティビティ フィードに表示されます。 ユーザーは、現在の更新要求と以前の申請をすべて更新 アプリで表示することもできます。 さらに、誰でもテンプレートを作成し、更新要求を送信できます。

更新には、一般的なビジネス シナリオ用のすぐに使用できるテンプレートと、独自のテンプレートを作成するオプションの両方が付属しています。 誰でも新しい種類の更新プログラム用のテンプレートを作成できます。

## <a name="example-scenario"></a>シナリオ例

衣料品店の従業員は、毎日店を開いたり閉じたりする責任があります。 毎朝、シフト リーダーはストアのオープン更新プログラムを入力します。これは、更新 アプリのすぐに使えるテンプレートです。 この更新では、前の夜の閉店に関する問題について説明し、店舗の清潔さに関する質問に回答し、補充が必要な商品を報告します。 更新プログラムを送信すると、ストアのニーズと問題を迅速かつ効率的に伝えることができます。 また、毎日の更新により、ストアの関連付けによって、何がうまくいっているかを強調する機会が与わります。

店舗の製造施設では、従業員がモバイル デバイスを使用して更新で安全チェックを行います。

![モバイル デバイス上の週単位の安全性チュートリアル テンプレートの画像。](media/updates-mobile.png)

一方、リモート ワーカーのチームがストアの Web サイトを更新しています。 タイム ゾーンに分散しているため、毎日のスタンドアップ会議は便利ではありません。 代わりに、各チーム メンバーは、進捗状況に関する毎日の更新レポートをチーム リーダーに送信します。

[更新ルックブックをダウンロード](https://go.microsoft.com/fwlink/?linkid=2197649)して、更新でできることの他の例を確認します。

## <a name="required-permissions-and-licenses"></a>必要なアクセス許可とライセンス

更新をデプロイするには、次の項目のアクセス許可が必要です。

- Microsoft Dataverse データベースを作成する権限。

- [powerautomate.microsoft.com](https://powerautomate.microsoft.com/) のアカウント。

- ターゲット環境の管理者ロール。

- Power Automate、Office 365、または Dynamics 365 のライセンス。

- ユーザーが新しいテンプレートを設定するには、Microsoft Formsのライセンスが必要です。

## <a name="storage-with-microsoft-dataverse"></a>Microsoft Dataverse を使用したストレージ

共通データ モデル (CDM) は、Microsoft Dataverse のビジネス アプリケーションや分析アプリケーションで使用される共有データ言語です。 これは、Microsoft とそのパートナーによって公開された、一連の標準化された拡張可能なデータ スキーマで構成されており、アプリケーションとビジネス プロセス全体でデータとその意味の一貫性を実現します。 [Common Data Model](/common-data-model/) の詳細については、こちらをご覧ください。

テンプレートから作成された更新は、タイトル、詳細、テンプレート ID など、Microsoft Dataverse にデータを格納します。  [Microsoft Forms のデータの保存場所](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)の詳細。

>[!Note]
>Microsoft Forms サイトでフォーム テンプレートを削除すると、更新 テンプレートが破損し、ユーザーは更新プログラムを送信できません。 ユーザーが、Microsoft Formsで削除されたテンプレートを開こうとすると、"CDB TableNotFound" というエラーが表示されます。

## <a name="updates-teams-app-permissions"></a>Teams アプリのアクセス許可を更新する

更新 Teams アプリを使用すると、次の機能にアクセスできます。

- メッセージやデータを受信します。

- メッセージと通知を送信します。

- Teams が提供するヘッダーを必要とすることなく、個人用アプリとダイアログをレンダリングします。

- [名前]、[電子メールアドレス]、[会社名]、[優先する言語] などの個人用プロフィール情報にアクセスします。

- チーム メンバーがチャネルで提供するメッセージとデータを受信します。

- チャネルでメッセージと通知を送信する。

- チームの情報にアクセスする:
  - チーム名
  - チャネル リスト
  - 名簿 (チーム メンバーの名前と電子メール アドレス)

- チームの情報を使用してメンバーに連絡します。

## <a name="disable-the-updates-app"></a>更新 アプリを無効にする

更新 アプリは既定で使用できます。 Teams 管理センターでアプリを無効にできます。

  1. Teams 管理センターにサインインします。

  2. **[Teams アプリ]** > **[アプリの管理]** の順に移動します。

  3. 更新 アプリを検索します。

     [![Teams Apps > [アプリの管理] が強調表示されている管理 センター ナビゲーションのスクリーンショット。](media/manage-updates-small.png)](media/manage-updates.png#lightbox)

  4. [**更新**] を選択します。

  5. 切り替えを選択して、組織のアプリを無効にします。
    ![更新を有効または無効にするトグルの画像。](media/toggle-updates.png)

## <a name="pin-updates-to-teams"></a>更新を Teams にピン留めする

アプリのセットアップ ポリシーを使用すると、チームをカスタマイズして、ユーザーにとって最も重要なアプリをユーザーに固定できます。 このアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。

ユーザーに更新アプリをピン留めするには、グローバル (組織全体の既定) ポリシーを編集するか、アプリセットアップ ポリシーでカスタム ポリシーを作成して割り当てます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を参照してください。

## <a name="retention-policy"></a>アイテム保持ポリシー

更新 アプリから作成された更新は、現時点ではバックアップをサポートしていない既定の Microsoft Dataverse 環境に格納されます。 詳細については、「[環境のバックアップと復元の方法Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments)」をご覧ください。

フォームに格納されているデータは、テンプレート作成者がMicrosoft Forms Web アプリの **削除されたフォーム** タブからクリーンアップするまで削除されません。

## <a name="conditional-access-and-permission-policies"></a>条件付きアクセスとアクセス許可ポリシー

Teams の更新 アプリでは、現在、Microsoft Teams 用に設定されている条件付きアクセス ポリシーはサポートされていません。

[Teams アプリのアクセス許可ポリシーを](teams-app-permission-policies.md)使用して、更新を管理できます。

## <a name="data-limitations"></a>データの制限事項

各ユーザーは最大 400 個の更新テンプレートを作成でき、各テンプレートは、Microsoft Formsの現在の機能に基づいて最大 50,000 個の要求を収集できます。

## <a name="security"></a>セキュリティ

Teams 更新 アプリから、ユーザーは新しい更新プログラムを作成し、送受信した更新プログラムを表示できます。 ユーザーは、要求の閲覧者でない限り、他のユーザーによって作成された更新にアクセスできません。

>[!Note]
> 更新レポートが作成されたチャットまたはチャネルの一部であるか、テンプレート作成者が手動でビューアーとして追加する場合、ユーザーには要求の閲覧者ロールが与えられます。 レポートの作成時にそのロールが与えられなかった場合、要求に対してアクションを実行することはできません。
