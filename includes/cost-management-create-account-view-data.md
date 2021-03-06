---
title: インクルード ファイル
description: インクルード ファイル
services: cost-management
author: bandersmsft
ms.service: cost-management
ms.topic: include
ms.date: 04/26/2018
ms.author: banders
manager: dougeby
ms.custom: include file
ms.openlocfilehash: 1b65775ef5ad40ca9e9c1e2c96fe1c2b8d92afdc
ms.sourcegitcommit: e2adef58c03b0a780173df2d988907b5cb809c82
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32198857"
---
## <a name="view-cost-data"></a>コスト データの表示

Cloudyn による Azure コスト管理では、すべてのクラウド リソース データへのアクセスを提供します。 ダッシュボード レポートから、タブ付きビューで標準およびカスタムの両方のレポートを表示できます。 以下は、人気のあるダッシュボードと、コスト データをすばやく表示するレポートの例です。

![管理ダッシュボード](./media/cost-management-create-account-view-data/mgt-dash.png)

この例では、管理ダッシュボードは、すべてのクラウド リソースにわたる Contoso ビジネスの統合されたコストを示しています。 Contoso では、Azure、AWS、および Google を使用しています。 ダッシュボードでは、情報をひと目で確認し、レポートに簡単に移動することができます。  

ダッシュボードでのレポートの目的がわからない場合は、**i** 記号にポインターを置くと説明が表示されます。 完全なレポートを表示するには、ダッシュボード上の任意のレポートをクリックします。

ポータルの上部にあるレポート メニューを使用して、レポートを表示することもできます。 過去 30 日間の Contoso の Azure リソースの使用について見てみましょう。 **[コスト]** > **[コスト分析]** > **[Actual Cost Analysis]\(実績コスト分析\)** をクリックします。 レポートにタグ、グループ、またはフィルターのセットがある場合は、値をクリアします。

![実績コストの分析](./media/cost-management-create-account-view-data/actual-cost-01.png)

この例では、$75,970 は総コストで、予算は $130,000 です。

ここで、レポートの書式を変更し、グループおよびフィルターを設定して、Azure コストの結果を絞り込んでみましょう。 **日付範囲**を過去 30 日間に設定します。 右上で、列の記号をクリックして棒グラフとして書式設定し、[グループ] で **[プロバイダー]** を選択します。 次に、**[プロバイダー]** のフィルターを **[Azure]** に設定します。

![実績コスト分析のフィルター処理](./media/cost-management-create-account-view-data/actual-cost-02.png)

この例では、Azure リソースの合計コストは過去 30 日間で $3,839 でした。

プロバイダー (Azure) バーを右クリックし、**[リソースの種類]** にドリルダウンします。

![ドリル ダウン](./media/cost-management-create-account-view-data/actual-cost-03.png)

次の図は、Contoso に発生した Azure リソースのコストを示しています。 合計は $3,839 でした。 この例では、約半分のコストがローカル冗長ストレージに費やされ、残りの半分がさまざまな VM インスタンスに費やされていました。

![リソースの種類](./media/cost-management-create-account-view-data/actual-cost-04.png)

リソースの種類を右クリックし、**[コスト エンティティ]** を選択して、コスト エンティティと、リソースを消費したサービスを表示します。 DevOps の VM と Worker サービスに、この例では、それぞれ $486.60 と $435.71 費やしました。 両方の合計は $922 です。

![コスト エンティティとサービス](./media/cost-management-create-account-view-data/actual-cost-05.png)

クラウド請求データの表示に関するチュートリアル ビデオは、「[Analyzing your cloud billing data with Azure Cost Management Powered by Cloudyn](https://youtu.be/G0pvI3iLH-Y)」(Cloudyn による Azure Cost Management を使用したクラウドの課金データの分析) をご覧ください。
