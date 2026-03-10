# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p05 P05_2.2_特征嵌入的发展概况 -BV1WZUKBmEQA_p5-

![](img/2f873d97cff36be3ac0f07a9daf9d525_0.png)

So。Let's start off with this example right here so we have a simple linear machine learning problem so we formalize it here。

 we have our loss function， we have our training samples so and training samples and our goal is to learn shared mapping W across all training samples however。

 okay these training samples right here。Are not allowed to directly interact。

Okay so this is a drawback， which means i'm learning this mapping。

 but i'm not considering the similarity or the relationship between these points。

 so maybe this point is very similar to this one so I should kind of you know take that into consideration when learning my mapping function my shared mapping W so this kind of approach。

Looks at each data point individually right so we have what we call an individualistic approach so these are individualistic points the data samples they live independently on a highdiional manifold all right so so here even in so in manifold learning for example this is the high dimensional manifold you have different data points and you want to do regression problem so you want to identify a path here that regresses these points right so now this path is projected here into a two- dimensionmensional plane right and all of these points with a manifold there is a projection there we can see this beautiful projection but still even in this manifold learning that we're doing right here and we were able to let's say learn and discover very well。



![](img/2f873d97cff36be3ac0f07a9daf9d525_2.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_3.png)

The embedding manifold of the data okay or the manifold where the data is nested and lives they're still independent okay so in manifold learning we learn also how to calculate the similarity between points so remember here we want you know these two to be closed so the similarity here needs to be somehow preserved right so I didn't talk about this in detail but here the manifold learning is based also on kind of you know preserving the neighborhood so that's the idea so it preserves the neighborhood it tries to keep similar points in the original space similar in the target space but not how to it doesn't connect the points okay so here with manifold learning we have kind of taken one step forward which means we're not trying to use the original space we're trying to discover a space where that represents this。



![](img/2f873d97cff36be3ac0f07a9daf9d525_5.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_6.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_7.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_8.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_9.png)

structureture and the geometry and the distribution of the data very well。

 but however this space is still individualistic and means like it looks at each point kind of you know independently of all other points。

 there is no actual interaction like we're not using you know multiple interaction to kind of model or represent this manifold。



![](img/2f873d97cff36be3ac0f07a9daf9d525_11.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_12.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_13.png)

Now。We're actually one step away from that， so let's look next so here this is you know。



![](img/2f873d97cff36be3ac0f07a9daf9d525_15.png)

The data， the input data that we have， let's say that the data structure on the manifold or distribution looks like this。

And then what all we need to do is actually to be able to model the interactions and include the interactions between these points during our learning is to learn what we call the adjacency matrix or to define the adjacency matrix of all these points so here we have all our training points so if we have n points we will have n by n matrix and in this matrix this will be the matrix that represents or encode the interaction between all points so for example here we may have a graph that looks like this all right so something like that and these will be connected in this way which means we'll have a sparse graph because in this example these two nodes let's take a different color。

So these two nodes are actually not connected directly okay so their connection is zero right so these also two nodes are not directly connected so you can see that in this graph so here we build a graph and this graph allows us to model the interaction between different points and when we are learning how to embed you know a single point right here okay so let's take a single point so if we learn how to embed this point or represent this point X I into a new dimensional space I'm going to take into account its interaction with its neighbors so now we're learning the embedding of this guy not with respect to only one single sample in terms of similarity but by looking at its you know kind of neighborhood。

All right， and this is very important because here we're trying to learn a structured manifold。

 a manifold that is encoded in a graph and this manifold will allow us to better represent the data because now we're not looking at these guys independently okay we're not training the model independently actually these guys are interconnected many of them happen to be very similar to one another so many of them happen to be you know close to one another so we're somehow building a huge graph that connects all these points and you know like if the points are very close so they will be within the same kind of graph or module and if they're far far away they will have kind of this these long distances between them okay or long edges so the idea here is that not to learn independently but to co-learn and this has a very interesting aspect because if I look at this point。

Without considering all of these somehow it's very reductionist。

 but if I look at this point and I consider its relationship with all other guys whether it's connected or disconnected then I am taking into account the similarity in the distribution of the training points in that particular training set or cohort or batch and I will be able to kind of learn better okay so this is you know basically it uses a graph to model and capture the relationships between pairs of data points and each sample interacts with other with all other points so this is the second learning paradigm so the first learning learning paradigm uses individualistic points and the second learning paradigm where we actually define a graph that encodes the relationship or represents or models the interaction weights and strength between different data samples。



![](img/2f873d97cff36be3ac0f07a9daf9d525_17.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_18.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_19.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_20.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_21.png)

Now we move to the collectivist learning paradigm where we have collectivist points and data points actually they co-in they co-learn together via this graph structure matrix a okay so of course here so this is our graph we have the features we define our adjacency matrix here we have you know a few node that are similar so they are connected and we can look at the topology of the graph that structure the connections between these different nodes where we want to learn the embedding or predict the label of this node we we should not predict the label of this node independently we should predict the label of this node dependent from it neighboring similar nodes okay so that's the basic idea and of course here we can add edge features。

And we can so we can in addition to we can add node features so we have the features here for nodes we can add edge features and remember we've got a graph to learn on now okay cool so now that we moved from all of this you know machine learning to manifold learning and then from manifold learning to graphbased you know learning these concepts now now that we have a graph so then we can do for example classification using this graph so we encode the data we represent the data as a graph and then we we will learn today about a simple graph neural network which is GCN so we'll see this later so we can apply a graph neural network here that allows us to kind of learn the embeddings of each node so we learn how to embed encode each node on the graph okay so now it's not just on a man。



![](img/2f873d97cff36be3ac0f07a9daf9d525_23.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_24.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_25.png)

Folder and use face but on this graph and this graph embedding of each of its nodes will allow us to kind of you know integrate this knowledge and classify for example the graphs so how do we actually get the node features okay how to how to get the edge or graph feature so this is a big question here so you may think okay so now。



![](img/2f873d97cff36be3ac0f07a9daf9d525_27.png)

We have modeled the data as a graph。

![](img/2f873d97cff36be3ac0f07a9daf9d525_29.png)

We need to kind of define extract features from the graphs because if you think about this as a sample right so this is for example。

 let's say I have a sample like this so this is my graph。It looks like this。

Allright and I' have the connectivity matrix a so how to extract features from this graph so I need to classify this graph I need to know if this graph is for example this molecule if it's a molecule I want to know if this molecule is you know poisonous or is it harmless right so basically to know that we need to we need to kind of extract features so the next step here is how to extract features feature extraction from a from the graph。

From only a so for now we have only the structure of the graph encoded in the adjacency matrix all right so we're gonna to take a very simple example here and yeah so there are in graph theory there are so many methods that allow us to you know like extract features for nodes edges graphs okay and the simplest ways so i'm going to cover these but if you guys are interested to learn more about you know these approaches you can read on that and I'll provide a few resources in the video caption below and you can also have a look at the graph theory playlist so I cover many of these fundamental classical feature extraction methods so there are three types here and I'm gonna to give you just a few simple examples so nodebased features edge based features and graphbased features so let's start with for example the node base。



![](img/2f873d97cff36be3ac0f07a9daf9d525_31.png)

Features so here node based features as you guys we guys remember in the first lecture we talked about centrality measures and topological roles and topological kind of values right so measures that we can use to characterize the importance of a node for example。

 here we can extract you know node based features so this graph G so this is graph for example。

Gee so what we need to do we kind of need to calculate or extract for each node if we're going to do node based classification right so we need to。

Extract。Features。For each node so for example for node let's call it X so this or node I so for simplicity so for node I I want to extract a set of features let's call this X I belonging to RD so I want to extract D features so for example I can use what we call centrality measures。

Or topological measures， for example， we have seen before degrees centrality okay so you can use between a centrality these are measures that allow us to quantify the importance of a node in a graph so if the node is a hub node is it a peripheral node is it a a node that you know like connects different parts of the graph so it's very important so we can use these topological measures and by doing so for example here if we use the degree so the degree of this node is three so we can put three here and you guys can see that manually we can extract these features only from the topology of the graph okay so each node I will be represented by this vector and then we can learn on this node so this node here for example could be a let's say。

If we want to predict you know trees and you have I don't know birds right。

 so maybe these will be birds and this will be a tree because they are close to。

And here's something is of this maybe we should change that a little bit so anyway far away you can see this actually it's connected far away。

 but the idea here is we want to get the label and the label here will depend on this feature so we can train for example an sVM classifier on these features that we extracted from our graph for each node okay so right so now the edge based features。



![](img/2f873d97cff36be3ac0f07a9daf9d525_33.png)

The simplest way is， let's say so we have a graph， so this is our graph here。

And we have our adjacency matrix， so this is an undirected binary graph and if it's also weighted graph what we can do。

 we can simply vectorize the upper triangular part of diagonal because the diagonal is self connection so we may not need that here。

 so we take the upper triangular。Part okay， and then we vectorize it。 And if you have n by n matrix。

 the upper triangular part will be n times n 1 divided by2。

 So this is the size of the feature vector x that we have extracted right here and this is edge base So here we have actually vectorized the whole the whole graph。

 So the weight of each you know edge may be discriminative so we can use this weight to do some some classification。

 but it's not very important here。 so let me actually move this。Right here。

 so it's better to kind of。Move it right here because there are different ways of doing this。

 but I' will explain so here if we if we cancatenate this is a way of vectorizing the matrix。

 but what we want we want actually to distinguish or to extract features for different edges okay so one way is if you want to represent the whole graph you can stack them also so here we actually extracted age based features and by stacking them。

Okay， all these weights。We get a feature vector that represents the graph Okay。

 so this represents the whole。Graph and this is the graph is equal to V E， and it has the matrix a。

 all right， so this feature vector represents the whole graph Now if you want edge based having a single you know value is not important。

 so let's let me take this back。 So here。A single value means one value right here。

 so this is the weight that connects。Notes I and a J okay I and J and could be， for example， 0。

5 so if you're going to rely only on this， you have only one feature。

So we want to extract multiple features for the single edge， so a single edge。Let's call it EIJ。

Will be represented by many features。Byy a。Of features。

So this set of features we can first call this set you know so EIJ will be represented by a vector X and in this vector X we're going have we can have the weight so we can put the weight okay WIJ and we need to identify or define different features so one feature here is also centrality measures so you can have for example between a centrality for edges for the edge connectivity so basically this tells us if this edge is so important it lies between all paths that connect you know all pairs of nodes between in the graphs if you take any pair of node it means that you need to traverse to walk through this edge okay to get from a from a to B to get from for example from this node let me choose different from this node A to no。

B or let's say B is here。 you always need to kind of most of the time you need to traverse this path so this path has a high between us。

 if it has high between us， it means it lies between all pairs of nodes and walks that connect them so this is also topology so you can do or extract a lot of topological or topology driven measures that allow you to put values here quantify or measure。

 the importance of each edge in the graph so this is for a single edge and now once we have this vector we can apply a linear for example。

 regression model because this will belong to RD， this is our sample here and for each edge we're gonna to have our training sample if we have some also target scores or target values we can learn a mapping through W as we have seen earlier to be able to predict this so basically these are basic techniques and you have also walks。

walkals on graphs number of walks on graphs so you can calculate the number of walks。

 the average walk on a single edge and have a number there and you put it here in this vector okay now for the graph based features。



![](img/2f873d97cff36be3ac0f07a9daf9d525_35.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_36.png)

So for the graph based features we can either you know like extract the features of the whole graph from edge features or from node features and we can combine both like for example here we combine different edge weights so this is if you take this as one feature representing one edge then if you stack them all together you're going to get that we can what we can also do is to you know concatenate or。



![](img/2f873d97cff36be3ac0f07a9daf9d525_38.png)

To add up， combine。So this is you know one way combine node features okay so you combine node features into a vector that represents the graph so if you have the centrality measure of all these guys so you have centrality measures of these kind of nodes you can just stack them all together and this will represent your graph G okay so that's another way if you're classifying graphs or you're like learning from graphs。

 so however so all of these are traditional methods they extract features using the a matrix okay so all of these methods these conventional methods they cannot。



![](img/2f873d97cff36be3ac0f07a9daf9d525_40.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_41.png)

Use node edge or graph features， so which means they don't use the a the feature matrix X and the E matrix here。

 So they are only relying on the adjacency matrix， which is the the top the structure of the graph Okay so all of these methods are are cannot integrate that。

 So these are basic graph theory analysis methods。 And these approaches cannot obtain embeddings for nodes。

 not in the training set。 Okay so so here we cannot get embeddings we cannot learn how to represent a node in a lower dimensional space。

 so if we add， for example， in node we need to calculate。

 So there is a type of here So we need to kind of recalculate all node feature representation。

 So we need to re。

![](img/2f873d97cff36be3ac0f07a9daf9d525_43.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_44.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_45.png)

P late， okay。So if we recalculate all no teacher representations that wouldn't be efficient okay so what that means if。

We have a graph like this and we classify the node in the graph， and I have a new note。All right。

 so for example。I add a new node here and I want to know the label so if you guys know this now that we have changed the topology of the graph so this is we need to update the a。

 we need to learn the centrality because now this node has two neighbors not only one right so every time you add a node all these features will change that the static features that we extract it which is' not good it means that you know you need to recalculate and update all these features again and these approaches cannot do not allow you to easily extract these you know features again for an unknown node so doing this for unknown nodes may not work so that's you know kind of these are the main advantages disadvantages sorry the main disadvantages of using classical graph theory to extract features and represent parts of graphs or the whole graphs the entire。

Graphs so so that's the story so I think we can actually stop here in the question that may come to your mind all right now that we're having you know all these that we represented our data in a collectivist way we have a graph that allows us to co-learn and benefit from other nodes right not just solving the task just for myself being individualistic here so we're trying to kind of build a community of nodes and we co-learn together however if we're going to use classical methods。

 these classical methods they do not embed or allow us to have annotated graphs which means graphs with node that have original extra features edges that have extra features also when we add a new node we need to recalculate all these classical node edge or graphbased feature measures or extraction。



![](img/2f873d97cff36be3ac0f07a9daf9d525_47.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_48.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_49.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_50.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_51.png)

![](img/2f873d97cff36be3ac0f07a9daf9d525_52.png)

Values right extracted values for all these nodes so that's not good now this is where gCN comes into play and comes as a solution for this so we will see this in the second section。



![](img/2f873d97cff36be3ac0f07a9daf9d525_54.png)