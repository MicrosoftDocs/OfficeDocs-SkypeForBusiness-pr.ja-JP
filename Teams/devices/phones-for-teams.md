---
title: Microsoft Teams 用の電話機
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: この記事では、Microsoft Teams 用に認定されている電話機と、それらの電話機でサポートされている機能のリストを取り上げています。
ms.openlocfilehash: cd38586b67f728febb4a43d3f018875b378cffd8
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962848"
---
# <a name="phones-for-microsoft-teams"></a>Microsoft Teams 用の電話機

Microsoft Teams では、従来の電話機エクスペリエンスを必要とするユーザー向けに卓上電話機製品をサポートしています。 この記事では、Teams 電話の包括的な概要を説明し、Microsoft 電話システムソリューションの一部として Microsoft Teams 電話の計画、配布、管理を行う方法について説明します。 

高品質で信頼できる Microsoft Teams を携帯電話で実現するために、お客様は、Lenovo、Polycom、および Audiocodes を使用して、さまざまな卓上電話と会議室のオーディオデバイスを開発し、認定しています。 Teams デバイスに関する最新情報と最新情報を取得するには、「 [Teams Marketplace](https://office.com/teamsdevices)」を参照してください。

電話を管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「 [Microsoft teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」を参照してください。

## <a name="features-supported-by-teams-phones"></a>Teams 電話でサポートされている機能
チームで認定された電話には、ユーザーがジョブを実行し、使用を管理するためのさまざまな機能が用意されています。 ここでは、Teams で認定された電話で利用できる機能の概要を説明します。

- **認証** 電話は先進認証を使用して、サインインとセキュリティを強化します。 ユーザーは、電話にユーザー名とパスワードを入力するか、PC/smartphone などの別のデバイスからサインインしてサインインできます。
- **スピードダイヤルと通話履歴** ユーザーは、連絡先、通話履歴、ボイスメールにすばやくアクセスできます。 相手は連絡先を簡単に管理し、電話から直接通話を発信できます。
- **会議と通話** ユーザーは、チームのワンタッチ結合を使って、スケジュールを表示して、簡単に会議に参加することができます。
- **通話グループ** 通話グループに参加している電話の担当者は、通話の可用性を簡単に管理し、通話キューからの着信を承諾または拒否することができます。
- **ユーザーの委任** エグゼクティブアシスタントと管理者は、経営陣による通話の傍受を管理することができます。エグゼクティブの代理として通話を発信してください。エグゼクティブが保留にした通話を引き継ぐことができます。エグゼクティブが通話中であるか、保留中であるかを監視します。
- **ホット desking** ユーザーは、電話にサインインするだけで、連絡先、会議、その他の環境設定を取得できます。 完了したら、サインアウトして、次のユーザーのために電話を残しておくことができます。
- **ビデオ** ビデオをサポートしている電話では、ユーザーは自分のコンピューターの場合と同様に、通話やビデオ会議に参加できます。 ユーザーは、携帯電話のカメラシャッターとマイクミュートスイッチを使用して、プライバシーを維持することができます。
- **共同** 作業の向上64ビット版の Teams デスクトップクライアントを実行している Windows PC に接続している場合、固定された方法で電話をロックおよびロック解除することができます。
- **アクセシビリティ** 電話には、他のユーザーが簡単に使用できるように、ハイコントラストテキストなどのいくつかのアクセシビリティ機能があります。
- **動的で強化された E911 のサポート** 911を呼び出すサインインしたユーザーは、電話でその場所を確認できます。 
    > [!IMPORTANT]
    > 電話にサインインしていない場合や、インターネットに接続されていない場合は、911通話を発信することはできません。 この問題が発生すると、電話に通知が表示されます。

上記の機能に加えて、電話にサインインしているユーザーに割り当てられているライセンスと電話ポリシーの種類に応じて、使用できる機能を制御することができます。 たとえば、個人アカウントで電話にサインインしたユーザーは、通話、会議、ボイスメールなどのさまざまな機能にアクセスできます。 電話にサインインする一般的な市外局番のライセンスが割り当てられているアカウントは、限られた範囲の機能にしかアクセスできません。通話履歴と会議のスケジュールは保持されないことがあります。たとえば、ユーザーのプライバシーを保護することができます。

## <a name="required-licenses"></a>必要なライセンス

Microsoft Teams ライセンスは、 [microsoft 365 および Office 365 サブスクリプション](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)の一部として購入できます。 電話で Microsoft Teams を使用するために必要なライセンスの詳細については、利用可能な[電話システムライセンス](https://products.office.com/microsoft-teams/voice-calling)を参照してください。

Teams の入手方法については[Microsoft Teams へのアクセス権を取得するにはどうしたらよいですか?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)を参照してください。

## <a name="deploy-your-phones-via-intune"></a>Intune で電話を展開する

### <a name="conditional-access"></a>条件付きアクセス

条件付きアクセスは、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されるようにするために役立つ Azure Active Directory 機能です。  条件付きアクセスポリシーを Teams サービスに適用する場合、access Teams が Intune に登録されている必要があり、その設定がポリシーに準拠する必要があります。  デバイスが Intune に登録されていない場合、または登録されているが、その設定がポリシーに準拠していない場合は、条件付きアクセスによって、ユーザーがデバイス上の Teams アプリにサインインしたり、使用したりするのを防ぐことができます。

通常、Intune で定義されているコンプライアンスポリシーは、ユーザーのグループに割り当てられます。  つまり、Android のコンプライアンスポリシーを user@contoso.com に割り当てると、そのポリシーは Android スマートフォンと、user@contoso.com によってサインインされる Android ベースの Teams デバイスに同じように適用されます。

Intune の登録を適用する必要がある条件付きアクセスを使用する場合、組織では、Intune 登録が成功するためにセットアップする必要があることがいくつかあります。

- **Intune ライセンス** Microsoft Teams 電話にサインインしているユーザーは、Intune のライセンスが必要です。  Microsoft Teams の電話番号が有効な Intune ライセンスを持つユーザーアカウントにサインインしている限り、その電話はサインイン処理の一環として Microsoft Intune に自動的に登録されます。
- **Intune を構成する** Android デバイス管理者登録用に、適切に設定された Intune テナントが必要です。

### <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Teams Android ベースのデバイスを登録するように Intune を構成する

Teams Android ベースのデバイスは、Intune で Android デバイス管理者 (DA) 管理によって管理されます。 デバイスを Intune に登録する前に、いくつかの基本的な手順を実行する必要があります。  既に Intune でデバイスを管理している場合は、次のことを行っている可能性があります。  そうでない場合は、次の操作を実行します。

1. Intune MDM (モバイルデバイス管理) 権限を設定します。  まだ Intune を使用していない場合は、デバイスを登録する前に MDM の権限を設定する必要があります。 詳細については、「 [モバイルデバイス管理機関を設定する](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)」を参照してください。  これは、新しい Intune テナントの作成時に行う必要がある1回限りの手順です。
2. Android デバイス管理者の登録を有効にします。 Android ベースの Teams デバイスは、Intune でデバイス管理デバイスとして管理されます。  新しく作成されたテナントの場合、デバイス管理者の登録は既定で無効になっています。  詳細については、「 [Android デバイス管理者の登録](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)」を参照してください。
3. ライセンスをユーザーに割り当てます。 Intune に登録しているチームデバイスのユーザーには、有効な Intune ライセンスが割り当てられている必要があります。 詳細については、「 [ユーザーにライセンスを割り当てて、ユーザーが Intune にデバイスを登録できるようにする](https://docs.microsoft.com/intune/fundamentals/licenses-assign)」を参照してください。
4. デバイス管理者のコンプライアンスポリシーを割り当てます。  Android デバイス管理者のコンプライアンスポリシーを作成して、チームデバイスにサインインするユーザーが含まれている Azure Active Directory グループに割り当てます。 詳細については、「 [コンプライアンスポリシーを使用して、Intune で管理しているデバイスのルールを設定する](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)」を参照してください。

## <a name="manage-your-phones"></a>電話を管理する

テナント管理者は、Teams 管理センターを使用して、チームのすべてのデバイスを管理し、最新の状態に保つことができます。 詳細については、「 [Microsoft Teams でデバイスを管理する](https://docs.microsoft.com/microsoftteams/devices/device-management)」を参照してください。 

## <a name="see-also"></a>関連項目

[Teams Marketplace](https://office.com/teamsdevices)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)
