# Login-Page
Login page using php and MySQL.
<?php
session_start();
if(empty($_SESSION)){
    header('Location:index.php');
}
?>
<html>

<head>
    <title>Zomato Home</title>
    <link rel="stylesheet" type="text/css" href="css/style.css">

    <!--Bootstrap CDNs-->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    <link rel="stylesheet" type="text/css" href="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">
    <script src="https://code.jquery.com/jquery-3.4.1.min.js" integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo="
            crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>

</head>

<body style="background-color: #f2f2f2">

<?php include "includes/header.php"; ?>

<div class="container">
    <div class="row mt-50">
        <div class="col-12">
            <div class="row">
                <div class="col-3">
                    <div class="card bg-warning">
                        <div class="card-body">
                            <h1 class="text-light">Discount #1</h1>
                        </div>
                    </div>
                </div>
                <div class="col-3">
                    <div class="card bg-danger">
                        <div class="card-body">
                            <h1 class="text-light">Discount #2</h1>
                        </div>
                    </div>
                </div>
                <div class="col-3">
                    <div class="card bg-info">
                        <div class="card-body">
                            <h1 class="text-light">Discount #3</h1>
                        </div>
                    </div>
                </div>
                <div class="col-3">
                    <div class="card bg-success">
                        <div class="card-body">
                            <h1 class="text-light">Discount #4</h1>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-12">
            <div class="row mt-50">
                <div class="col-9">
                    <div class="row">
                        <div class="col-12">
                            <div class="card">
                                <div class="card-body">
                                    <div class="row">
                                        <?php
                                        $connection=mysqli_connect("localhost","root","","zomato");
                                        $result=mysqli_query($connection,$query);

                                        while($row=mysqli_fetch_array($result)){
                                            echo '<div class="col-4">
                                            <div class="card">
                                                <img src="img/'.$row['r_bg'].'" class="card-img-top">
                                                <div class="card-body">
                                                    <h4 class="card-title">'.$row['r_name'].'</h4>
                                                    <p class="card-text text-grey">
                                                    '.$row['r_cuisine'].'
                                                        Chinese,Tibetese,Indian
                                                    </p>
     <!--how change or send particular id to next page-->                                              <a href="menu.php?id='.$row['r_id'].'"class="btn btn-success btn-block">View Menu</a>
                                                </div>
                                            </div>
                                        </div>';
                                        }


                                        ?>
                                        ?>
                                        <div class="col-4">
                                            <div class="card">
                                                <img src="https://cms.qz.com/wp-content/uploads/2017/09/africanfoodcollage-e1506542312548.jpg?quality=75&strip=all&w=410&h=308.0150753768844" class="card-img-top">
                                                <div class="card-body">
                                                    <h4 class="card-title">Momo I am!</h4>
                                                    <p class="card-text text-grey">
                                                        Chinese,Tibetese,Indian
                                                    </p>
                                                    <a class="btn btn-success btn-block">View Menu</a>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-3">
                    <div class="card bg-nav">
                        <div class="card-body">
                            <h1 class="text-light">Stupid Ads</h1>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>


</body>


</html>
