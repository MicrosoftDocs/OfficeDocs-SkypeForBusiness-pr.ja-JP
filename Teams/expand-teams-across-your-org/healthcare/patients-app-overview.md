---
title: 'Teams 管理者用の患者アプリ '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: Teams 管理者用の患者アプリ
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749559"
---
# <a name="patients-app-overview"></a>Patients アプリの概要

患者アプリケーションは、Microsoft Teams ストアアプリで、すべての Teams ユーザーが利用できます。 このアプリを使用すると、患者の治療チーム (看護師、医師、社会員など) が患者の一覧を表示して、ラウンドやアプリの会議から一般的な患者の監視まで、患者のリストを確認できます。   

このアプリには、次の2つのモードがあります。 

- Emr から FHIR に接続する EMR 接続モード。 EMR 接続モードのアプリはプライベートプレビューのままであり、ユーザーまたは管理者は、Office 365 テナントに関する情報を使用して teamsforhealthcare@service.microsoft.com に Microsoft をドロップして、アプリへのアクセスを要求することがあります。 
- 治療チームが患者情報を手動で追加/取り込みできる手動モード。 このアプリケーションは、Teams app store で利用できます。これは、エンドユーザーが既定でダウンロードするためであり、パブリックプレビューに含まれています。 [Microsoft Teams のアプリセットアップポリシー](../../teams-app-setup-policies.md)を使用するユーザーの特定のセクションにアプリを制限することができます。



## <a name="usage-example"></a>使用例

医療 wards の各シフトでの丸めセッション中に、clinicians は nursing ステーションで収集して、の患者との進行状況に関する最新の更新について話し合うことができます。  また、重要な指標 (医療、患者の医療記録での明示的なものではありません) を強調表示し、お客様の診断に基づいて患者が適切なグライドパス上にいることを確認します。 このような患者を丸めるために、クレジットの追加により、すべての clinicians が追加され、患者リストに患者が追加されるようになります。 ラウンドでは、患者との間の看護師とその他のケア givers によって、モバイルデバイス上の Microsoft Teams と患者アプリの情報が更新され、お客様のデバイスに関連する患者情報が更新され、ケアチーム内の他の参加者に対してそれらの更新とメモを表示することができます。常に同期します。1日に2回、シフトの開始時と終了時には、マルチ displicinary のチーム会議も用意されています。これには、患者リストを経由して患者の一覧を表示したり、患者のアプリを使って患者の情報を共有したりできます。 場合によっては、特定の clinicians が、それらのチーム会議にリモートでダイヤルインしても、ディスカッションの一部となることがあります。 

## <a name="configure-patients-app"></a>患者のアプリを設定する

EMR モードの患者アプリを使用するように環境を準備する方法について詳しくは、「 [Microsoft Teams への電子医療記録の統合](patients-app.md)」をご覧ください。 また、組織で患者のアプリを有効にするには、「 [Microsoft Teams でアプリセットアップポリシーを管理](../../teams-app-setup-policies.md)する」を参照する必要があります。

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a>関連項目

[電子医療記録を Microsoft Teams に統合する](patients-app.md)
