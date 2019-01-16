
"# QuantLib_LLM" 
We are going to build the quantlib for LLM only. 
LLM : Libormarketmodel.cpp 

 NOW, I am going to generate LLM: LiborMarketModel !  
estsuiteLLM : 

   Configuration General: Output Directory : bin\

   Target extension: .exe 

   Configuration type : Application(.exe)

   VC++ Directories : Include Directories : $(BOOST_ROOT); ..\    (return to parent directory)

   Reference Directories : ..\lib only for calendar.cpp  


   (should be :  $(BOOST_ROOT)\libs; ..\lib  LLM )
  C/C++
   Additional Include Directories : $(BOOST_ROOT); ..\ 

   Linker : Additional Library Directories : $(BOOST_LIBRARYDIR) ; ..\lib 


   NOW, I am going to generate LLM: LiborMarketModel !  

Now I need to find out all dependencies : 


utilities.hpp contains 



#include <ql/instruments/payoffs.hpp>
   #include <ql/option.hpp>solved. 
      #include <ql/instrument.hpp>solved
         (#include <ql/patterns/lazyobject.hpp>
         	[#include <ql/patterns/observable.hpp>] solved 
         	 {#include <ql/errors.hpp>
         	 	  (#include <ql/qldefines.hpp>-none 
                   #include <ql/shared_ptr.hpp>
                       [<ql/qldefines.hpp>]-meet)
               #include <ql/types.hpp>
                  (#include <ql/qldefines.hpp> meet
               	  )
               #include <ql/patterns/singleton.hpp>
                  (#include <ql/qldefines.hpp>-meet)

               #include <ql/shared_ptr.hpp> -meet}
          #include <ql/pricingengine.hpp> solved. 
            [#include <ql/patterns/observable.hpp>]-meet
          #include <ql/utilities/null.hpp>
            [#include <ql/types.hpp>]-meet 
          #include <ql/time/date.hpp>)
            [#include <ql/time/period.hpp>
                  {#include <ql/time/frequency.hpp>
                  	(#include <ql/qldefines.hpp>)-meet
                   #include <ql/time/timeunit.hpp>
                    (#include <ql/qldefines.hpp>)-meet
                   #include <ql/types.hpp>-meet}
             #include <ql/time/weekday.hpp>
                 (#include <ql/qldefines.hpp>-meet)
              #include <ql/utilities/null.hpp>-meet]
   #include <ql/payoff.hpp>
      #include <ql/types.hpp>
         (#include <ql/qldefines.hpp>)-meet
      #include <ql/patterns/visitor.hpp>
         (#include <ql/qldefines.hpp>)-meet
      #include <ql/errors.hpp>
          (#include <ql/qldefines.hpp> - meet
           #include <ql/shared_ptr.hpp>)-meet 
#include <ql/exercise.hpp> solved.
      {#include <ql/time/date.hpp> -meet}
#include <ql/termstructures/yieldtermstructure.hpp> solved. 
      { #include <ql/termstructure.hpp>-solved
      	    [#include <ql/time/calendar.hpp>-solved. 
      	       (#include <ql/errors.hpp>-meet 
                  #include <ql/time/date.hpp>-meet 
                 #include <ql/time/businessdayconvention.hpp>
                  {#include <ql/qldefines.hpp> -meet }
                  #include <ql/shared_ptr.hpp>-meet )
             #include <ql/time/daycounter.hpp> solved/
                (#include <ql/time/date.hpp> meet 
                 #include <ql/errors.hpp> meet )
            #include <ql/settings.hpp> solved
                (#include <ql/patterns/singleton.hpp> meet
                #include <ql/time/date.hpp> meet 
               #include <ql/utilities/observablevalue.hpp>
                {#include <ql/patterns/observable.hpp> meet})
            #include <ql/handle.hpp> solved
                (<ql/patterns/observable.hpp>-meet)
            #include <ql/math/interpolations/extrapolation.hpp> meet 
             (<ql/qldefines.hpp> meet)
             #include <ql/utilities/null.hpp> meet]
        #include <ql/interestrate.hpp> solved
            [#include <ql/compounding.hpp>
              (#include <ql/qldefines.hpp> meet)
             #include <ql/time/daycounters/actual365fixed.hpp>
             (#include <ql/time/daycounter.hpp> meet)
             ]
        #include <ql/quote.hpp> solved
           [#include <ql/handle.hpp> meet
            #include <ql/errors.hpp> meet 
            #include <ql/utilities/null.hpp> meet]}
    #include <ql/termstructures/volatility/equityfx/blackvoltermstructure.hpp> solved
     {#include <ql/termstructures/voltermstructure.hpp> solved. 
     	[#include <ql/termstructure.hpp> meet ]
      #include <ql/patterns/visitor.hpp>solved. 
       [#include <ql/qldefines.hpp> meet]}
#include <ql/quote.hpp>-meet 
#include <ql/patterns/observable.hpp> -meet 
#include <ql/time/daycounters/actual365fixed.hpp>-meet 








quantlibtestsuite.cpp {
#include <ql/types.hpp> meet
#include <ql/settings.hpp> meet
#include <ql/utilities/dataparsers.hpp>{#include <ql/time/date.hpp> meet}
#include <ql/version.hpp>{#include <ql/qldefines.hpp>}
}




ql/option.hpp
ql/instrument.hpp
ql/errors.hpp
ql/qldefines.hpp
ql/shared_ptr.hpp
ql/types.hpp
ql/pricingengine.hpp
ql/payoff.hpp
ql/exercise.hpp
ql/settings.hpp
ql/handle.hpp
ql/termstructure.hpp
ql/interestrate.hpp
ql/version.hpp
ql/quote.hpp





as long as they call ql/something, we can make stop ! 


libormarketmodel.cpp :{&
#include <ql/indexes/ibor/euribor.hpp> solved{
	#include <ql/indexes/iborindex.hpp> solved[
        <ql/indexes/interestrateindex.hpp>
        ( #include <ql/index.hpp> solved. 
             {#include <ql/time/calendar.hpp> solved. 
              #include <ql/math/comparison.hpp> solved. [
                  #include <ql/types.hpp> solved
                  #include <ql/shared_ptr.hpp>solved]
              #include <ql/indexes/indexmanager.hpp> solved. 
                  
                }

         #include <ql/time/calendar.hpp> solved. 
         #include <ql/currency.hpp>  
              {
              #include <ql/math/rounding.hpp> solved. 
              }
         #include <ql/time/daycounter.hpp> solved. 
         #include <ql/time/period.hpp> solved. 

        )

        <ql/termstructures/yieldtermstructure.hpp> solved. 
	]




#include <ql/instruments/capfloor.hpp> solved. {
	 
      #include <ql/cashflows/iborcoupon.hpp> solved. 
           [ #include <ql/cashflows/floatingratecoupon.hpp> meet(
                 #include <ql/cashflows/coupon.hpp> meet
                      {#include <ql/cashflow.hpp> meet 
                      	   [#include <ql/event.hpp> meet
                           ]
                      }
                
                
                
           	   )
           
             #include <ql/time/schedule.hpp> solved. 

            ]
     
      #include <ql/termstructures/volatility/volatilitytype.hpp> solved. 
          [ #include <ql/qldefines.hpp>  solved]
}

#include <ql/termstructures/yield/zerocurve.hpp> solved. M {
	#include <ql/termstructures/yield/zeroyieldstructure.hpp> 
	       [#include <ql/termstructures/yieldtermstructure.hpp> solved.M 
	              
	       ]
     #include <ql/termstructures/interpolatedcurve.hpp> solved. M
           [#include <ql/math/interpolation.hpp> solved. M 
              
         
           ]
     #include <ql/math/interpolations/linearinterpolation.hpp> solved. M 
          [#include <ql/math/interpolation.hpp> solved]
    
     
     #include <ql/utilities/dataformatters.hpp> solved M. 
         
    }


#include <ql/termstructures/volatility/optionlet/capletvariancecurve.hpp> solved. M.M. 
       {
       	#include <ql/termstructures/volatility/optionlet/optionletvolatilitystructure.hpp> solved
       	     [#include <ql/termstructures/voltermstructure.hpp> solved.
             #include <ql/termstructures/volatility/optionlet/optionletstripper.hpp>
                    (#include <ql/termstructures/volatility/optionlet/strippedoptionletbase.hpp>solved. 
                    	    {
                    	    	#include <ql/patterns/lazyobject.hpp> meet. 
                                #include <ql/time/businessdayconvention.hpp> solved. 
                                #include <ql/types.hpp> solved. 
                                #include <ql/termstructures/volatility/volatilitytype.hpp> solved. 
                    	    }
                     #include <ql/termstructures/volatility/capfloor/capfloortermvolsurface.hpp> solved. 
                             {
                             	#include <ql/termstructures/volatility/capfloor/capfloortermvolatilitystructure.hpp> solved. 
                             	        [#include <ql/termstructures/voltermstructure.hpp>] solved. 
                                  #include <ql/math/interpolations/interpolation2d.hpp> solved. M. 
                                        
                                  #include <ql/quote.hpp> meet 
                                 #include <ql/patterns/lazyobject.hpp> meet. 
                                 #include <ql/time/daycounters/actual365fixed.hpp> meet 
                             }
                     #include <ql/termstructures/volatility/volatilitytype.hpp> meet
                     #include <ql/termstructures/yieldtermstructure.hpp> meet 
                     )
              #include <ql/termstructures/volatility/volatilitytype.hpp> meet 
       	     ]
         #include <ql/termstructures/volatility/equityfx/blackvariancecurve.hpp> solved. 
               [#include <ql/termstructures/volatility/equityfx/blackvoltermstructure.hpp> meet 
                #include <ql/math/interpolation.hpp> meet 
                ]
        #include <ql/termstructures/volatility/flatsmilesection.hpp> solved. 
              [#include <ql/termstructures/volatility/smilesection.hpp>solved. 
                     (
                     	#include <ql/patterns/observable.hpp> meet 
                        #include <ql/time/daycounter.hpp> meet 
                        #include <ql/utilities/null.hpp> meet 
                         #include <ql/option.hpp> meet 
                         #include <ql/termstructures/volatility/volatilitytype.hpp> meet 
                     )
              ]

       }


#include <ql/math/optimization/levenbergmarquardt.hpp> solved. 
    {#include <ql/math/optimization/problem.hpp> solved. 
          [#include <ql/math/optimization/method.hpp>solved.
               (#include <ql/math/optimization/endcriteria.hpp> meet)
           #include <ql/math/optimization/constraint.hpp> meet
           #include <ql/math/optimization/costfunction.hpp> solved. M. 
                (#include <ql/math/array.hpp> meet
                #include <ql/math/matrix.hpp> meet
                 #include <ql/math/functional.hpp> meet )
          ]

    }

#include <ql/math/statistics/generalstatistics.hpp> solved. M.M. 
#include <ql/math/randomnumbers/rngtraits.hpp> solved. M.M. 

    {
        #include <ql/methods/montecarlo/pathgenerator.hpp> solved.M. 
               [ #include <ql/methods/montecarlo/brownianbridge.hpp> solved. 
                      (#include <ql/methods/montecarlo/path.hpp> solved. M. 
                        #include <ql/methods/montecarlo/sample.hpp> solved. M. 
                       )
                 #include <ql/stochasticprocess.hpp> meet 
                ]
        #include <ql/math/randomnumbers/mt19937uniformrng.hpp> solved. 
           [#include <ql/methods/montecarlo/sample.hpp> meet]
         #include <ql/math/randomnumbers/inversecumulativerng.hpp> solved. 
            [#include <ql/methods/montecarlo/sample.hpp> meet]
        #include <ql/math/randomnumbers/randomsequencegenerator.hpp> solved.
        #include <ql/math/randomnumbers/sobolrsg.hpp> solved. 
        #include <ql/math/randomnumbers/inversecumulativersg.hpp>  solved. M. 
        #include <ql/math/distributions/normaldistribution.hpp> solved.M. 
            [#include <ql/math/errorfunction.hpp> meet
             #include <ql/errors.hpp> meet]
        #include <ql/math/distributions/poissondistribution.hpp> Solved. M 
             [ #include <ql/math/factorial.hpp> solved. 
               #include <ql/math/incompletegamma.hpp> solved. M. 
            ]
    }
#include <ql/methods/montecarlo/multipathgenerator.hpp> solved.M. 
     {
     	#include <ql/methods/montecarlo/multipath.hpp> solved
     	     [#include <ql/methods/montecarlo/path.hpp> meet]
        #include <ql/methods/montecarlo/sample.hpp> meet 
        #include <ql/stochasticprocess.hpp> meet 
     }

#include <ql/pricingengines/swap/discountingswapengine.hpp> solved. M.M. 

    {
    	#include <ql/instruments/swap.hpp> meet
        #include <ql/termstructures/yieldtermstructure.hpp> meet 
        #include <ql/handle.hpp> meet 
    }
#include <ql/pricingengines/capfloor/blackcapfloorengine.hpp> solved. M.M. 
    {
    	#include <ql/instruments/capfloor.hpp> meet
        #include <ql/termstructures/volatility/optionlet/optionletvolatilitystructure.hpp> meet
    }
#include <ql/pricingengines/capfloor/analyticcapfloorengine.hpp> solved.M.M. 
    {
    	#include <ql/instruments/capfloor.hpp> meet 
        #include <ql/pricingengines/genericmodelengine.hpp> solved.M. 
            [ #include <ql/pricingengine.hpp> meet
             #include <ql/handle.hpp> meet 
            ]
        #include <ql/models/model.hpp> meet 
    }

#include <ql/models/shortrate/calibrationhelpers/caphelper.hpp> solved.M.M. 

    {
    	#include <ql/models/calibrationhelper.hpp> meet 
        #include <ql/instruments/capfloor.hpp> meet 
    }
#include <ql/models/shortrate/calibrationhelpers/swaptionhelper.hpp> solved.M.M. 
   {

   	#include <ql/models/calibrationhelper.hpp> meet
   #include <ql/instruments/swaption.hpp>  meet 
   #include <ql/termstructures/volatility/volatilitytype.hpp> meet 
   }






#include <ql/legacy/libormarketmodels/lfmcovarproxy.hpp> solved. M. 
    {
     #include <ql/legacy/libormarketmodels/lfmcovarparam.hpp> solved. M. 
          [#include <ql/math/matrix.hpp> solved. M. 
              (#include <ql/math/array.hpp> solved M 

              	    {

                       #include <ql/math/functional.hpp> solved M. 
                       #include <ql/utilities/disposable.hpp> solved M. 

              	    }

                 #include <ql/utilities/steppingiterator.hpp> solved M. 
              )
          ]
     #include <ql/legacy/libormarketmodels/lmvolmodel.hpp> solved. 
            [#include <ql/models/parameter.hpp> solved. 
                 ( #include <ql/math/optimization/constraint.hpp> solved. 

                 	{#include <ql/math/array.hpp> solved. M. }
                 	)
            ]
      #include <ql/legacy/libormarketmodels/lmcorrmodel.hpp> solved. {
      	  #include <ql/math/array.hpp> solved. 
          #include <ql/math/matrix.hpp> solved. 
          #include <ql/models/parameter.hpp> solved. 
      }
    }


#include <ql/legacy/libormarketmodels/lmexpcorrmodel.hpp> solved. {
	    #include <ql/legacy/libormarketmodels/lmcorrmodel.hpp> solved. 
    }
#include <ql/legacy/libormarketmodels/lmlinexpcorrmodel.hpp> solved. M. {
	#include <ql/legacy/libormarketmodels/lmcorrmodel.hpp> solved. 
}
#include <ql/legacy/libormarketmodels/lmfixedvolmodel.hpp> solved. M. {
	  #include <ql/legacy/libormarketmodels/lmvolmodel.hpp> solved. 
}
#include <ql/legacy/libormarketmodels/lmextlinexpvolmodel.hpp>{
	 #include <ql/legacy/libormarketmodels/lmlinexpvolmodel.hpp> solved. 
	   [#include <ql/legacy/libormarketmodels/lmcorrmodel.hpp> solved. ]
}
#include <ql/legacy/libormarketmodels/liborforwardmodel.hpp> solved. M.M. 
     {
      #include <ql/legacy/libormarketmodels/lfmprocess.hpp> solved. M. 
              [#include <ql/cashflow.hpp> solved. 
              #include <ql/indexes/iborindex.hpp> solved. 
                #include <ql/termstructures/volatility/optionlet/optionletvolatilitystructure.hpp> meet
                #include <ql/stochasticprocess.hpp> solved.M. 
                    (#include <ql/time/date.hpp> meet 
                     #include <ql/patterns/observable.hpp> meet 
                     #include <ql/math/matrix.hpp> meet  
                    	)
               #include <ql/legacy/libormarketmodels/lfmcovarparam.hpp>] meet 
      #include <ql/termstructures/volatility/swaption/swaptionvolmatrix.hpp> solved M. 
              [#include <ql/termstructures/volatility/swaption/swaptionvoldiscrete.hpp> solved.M. 
                    (
                    	 #include <ql/termstructures/volatility/swaption/swaptionvolstructure.hpp>
                    	       {
                    	       	#include <ql/termstructures/voltermstructure.hpp> meet 
                                 #include <ql/termstructures/volatility/volatilitytype.hpp> meet 
                    	       }
                        #include <ql/math/interpolation.hpp> meet 
                        #include <ql/patterns/lazyobject.hpp> meet 
                    	)
              #include <ql/math/interpolations/interpolation2d.hpp> meet 
               #include <ql/math/matrix.hpp> meet 
              ]
      #include <ql/termstructures/volatility/optionlet/capletvariancecurve.hpp> meet 
      #include <ql/models/model.hpp> solved.M. 
             [#include <ql/option.hpp> meet 
             #include <ql/methods/lattices/lattice.hpp> solved. M. 
                   (#include <ql/numericalmethod.hpp> solved. M. 
                   	      {
                   	      	#include <ql/timegrid.hpp> solved. 
                   	      	     [#include <ql/errors.hpp> meet 
                                  #include <ql/math/comparison.hpp> meet 
                   	      	     ]
                            #include <ql/math/array.hpp> meet 
                   	      }
                    #include <ql/discretizedasset.hpp>  solved. 

                            {
                            	#include <ql/numericalmethod.hpp> meet 
                                #include <ql/math/comparison.hpp> meet 
                                #include <ql/math/functional.hpp> meet 
                                #include <ql/exercise.hpp> meet 

                            }

                     #include <ql/patterns/curiouslyrecurring.hpp> solved. 
                   	)
             #include <ql/models/parameter.hpp> meet 
             #include <ql/models/calibrationhelper.hpp> solved. 
                   (#include <ql/quote.hpp> meet 
                   #include <ql/termstructures/yieldtermstructure.hpp> meet 
                    #include <ql/termstructures/volatility/volatilitytype.hpp> meet 
                    #include <ql/patterns/lazyobject.hpp> meet 
                   	 )
              #include <ql/math/optimization/endcriteria.hpp> solved. ]
      #include <ql/legacy/libormarketmodels/lfmcovarproxy.hpp> meet 
     }
#include <ql/legacy/libormarketmodels/lfmswaptionengine.hpp> solved. M.M. 
      {
      	#include <ql/instruments/swaption.hpp> solved. M. 

      	    {
      	    	 #include <ql/option.hpp> meet 
                #include <ql/instruments/vanillaswap.hpp> solved.  [
                    #include <ql/instruments/swap.hpp> solved. 
                   #include <ql/time/daycounter.hpp> meet 
                      #include <ql/time/schedule.hpp> meet 
                   ]
                #include <ql/termstructures/yieldtermstructure.hpp> meet 
                  #include <ql/termstructures/volatility/volatilitytype.hpp> meet 
      	    }
        #include <ql/pricingengines/genericmodelengine.hpp> solved. 
            {
            	#include <ql/pricingengine.hpp> meet 
               #include <ql/handle.hpp> meet 
            }
        #include <ql/legacy/libormarketmodels/liborforwardmodel.hpp> meet 
      }
#include <ql/legacy/libormarketmodels/lfmhullwhiteparam.hpp> solved. M.M. 
     {
     	#include <ql/legacy/libormarketmodels/lfmprocess.hpp> meet 
        #include <ql/legacy/libormarketmodels/lfmcovarparam.hpp> meet 
     }



this part is done !  
#include <ql/time/daycounters/actual360.hpp> solved. M. 
   {#include <ql/time/daycounter.hpp> solved. }
#include <ql/time/schedule.hpp> solved. 
#include <ql/quotes/simplequote.hpp> solved M{
	  #include <ql/quote.hpp>  solved. 
}

&}







we do not need to consider cpp file, as long as cpp file is not deleted. We do not care cpp include somethings !  
But If hpp constains hpp, we need to keep them. 
Now I am checking the second layer of hpp-cpp files, cpp is deleting safe or not !  
Now the conclusion is , as long as we have hpp files , we need to keep the corresponding cpp files. 
(The hpp file is from the libormarketmodel.cpp only, utilities.hpp files contains hpp is an exception). 

Now the linker has two part, one is lib of boost, the other is lib of quantlib.  We can waive the second one if the testsuite add Quantlib project as a reference !   




Files keep in each folder: 

Files keep in each folder: 

1. ql/cashflows/
ql/cashflows/iborcoupon.hpp
ql/cashflows/floatingratecoupon.hpp
ql/cashflows/coupon.hpp


2. ql/currencies
NONE 

3. ql/experimental/
NONE

4. ql/indexes/
   ql/indexes/ibor/
#include <ql/indexes/ibor/euribor.hpp>

   ql/indexes/inflation/
    empty
   ql/index/swap/
    empty



#include <ql/indexes/iborindex.hpp>
#include<ql/indexes/interestrateindex.hpp>
 #include <ql/indexes/indexmanager.hpp>
 #include <ql/indexes/iborindex.hpp>


5. ql/instruments/
   ql/instruments/bonds/  --empty 
  instrument: 

 #include <ql/instruments/payoffs.hpp>
 #include <ql/instruments/capfloor.hpp>
 #include <ql/instruments/swap.hpp>
 #include <ql/instruments/capfloor.hpp>
 #include <ql/instruments/swaption.hpp>  meet 
 #include <ql/instruments/vanillaswap.hpp>


6. Legacy  (do not delete)
   legacy/libormarketmodels/

   #include <ql/legacy/libormarketmodels/lfmcovarproxy.hpp>
    #include <ql/legacy/libormarketmodels/lfmcovarparam.hpp>
    #include <ql/legacy/libormarketmodels/lmvolmodel.hpp>
      #include <ql/legacy/libormarketmodels/lmcorrmodel.hpp>
      #include <ql/legacy/libormarketmodels/lmexpcorrmodel.hpp> 
      #include <ql/legacy/libormarketmodels/lmlinexpcorrmodel.hpp> 
     #include <ql/legacy/libormarketmodels/lmfixedvolmodel.hpp> 
     #include <ql/legacy/libormarketmodels/lmextlinexpvolmodel.hpp>
     #include <ql/legacy/libormarketmodels/liborforwardmodel.hpp>
        #include <ql/legacy/libormarketmodels/lfmprocess.hpp>
     #include <ql/legacy/libormarketmodels/lfmswaptionengine.hpp> 
    #include <ql/legacy/libormarketmodels/lfmhullwhiteparam.hpp>

7. ql/math/
     ql/math/copulas/   empty 
     ql/math/distributions/
         {
         	#include <ql/math/distributions/normaldistribution.hpp>
         	#include <ql/math/distributions/poissondistribution.hpp>
         }
     ql/math/integrals/   empty 
     ql/math/interpolations/ 
         {
         	#include <ql/math/interpolations/extrapolation.hpp>
         	#include <ql/math/interpolations/linearinterpolation.hpp>
         	#include <ql/math/interpolations/interpolation2d.hpp> 

         }
     ql/math/matrixutilities/ empty 
     ql/math/ode/   empty 
     ql/math/optimization/

         {
         	 #include <ql/math/optimization/levenbergmarquardt.hpp>
         	 #include <ql/math/optimization/problem.hpp> 
         	 #include <ql/math/optimization/method.hpp>
         	 #include <ql/math/optimization/endcriteria.hpp>
         	 #include <ql/math/optimization/constraint.hpp>
         	 #include <ql/math/optimization/costfunction.hpp>

         }
     ql/math/randomnumbers/

         {
         	#include <ql/math/randomnumbers/rngtraits.hpp>
         	 #include <ql/math/randomnumbers/mt19937uniformrng.hpp>
         	 #include <ql/math/randomnumbers/inversecumulativerng.hpp>
         	  #include <ql/math/randomnumbers/randomsequencegenerator.hpp>
         	  #include <ql/math/randomnumbers/sobolrsg.hpp> 
         	  #include <ql/math/randomnumbers/inversecumulativersg.hpp>

         }
     ql/math/solvers1D/  empty 
     ql/math/statistics/
      {
      	#include <ql/math/statistics/generalstatistics.hpp> 
      }

      ql/math/ files 
      {
      	 #include <ql/math/comparison.hpp>
      	  #include <ql/math/rounding.hpp>
      	  #include <ql/math/interpolation.hpp> 
      	  #include <ql/math/array.hpp>
      	  #include <ql/math/matrix.hpp> meet
          #include <ql/math/functional.hpp> meet 
          #include <ql/math/errorfunction.hpp
           #include <ql/math/factorial.hpp> solved. 
          #include <ql/math/incompletegamma.hpp> solved. M.
         
       finished !  great!      


      }
 8. ql/methods/ 
    ql/methods/finitedifferences
    ql/methods/lattices
       #include <ql/methods/lattices/lattice.hpp>
    ql/methods/montecarlo 
     #include <ql/methods/montecarlo/pathgenerator.hpp>
     #include <ql/methods/montecarlo/brownianbridge.hpp>
     #include <ql/methods/montecarlo/path.hpp>
     #include <ql/methods/montecarlo/sample.hpp> 
     #include <ql/methods/montecarlo/multipathgenerator.hpp>
     #include <ql/methods/montecarlo/multipath.hpp> 

 9. ql/models/
    (just keep a file in parent folder)
      ql/models/equity/   empty
      ql/models/marketmodels/  empty 
      ql/models/shortrate/
           #include <ql/models/shortrate/calibrationhelpers/caphelper.hpp>
           #include <ql/models/shortrate/calibrationhelpers/swaptionhelper.hpp>


       ql/models/volatility/  empty  


    #include <ql/models/model.hpp>
    #include <ql/models/calibrationhelper.hpp> 
    #include <ql/models/parameter.hpp>   

10. ql/patterns
    #include <ql/patterns/lazyobject.hpp>
    	#include <ql/patterns/observable.hpp>
    	#include <ql/patterns/curiouslyrecurring.hpp>
      #include <ql/patterns/singleton.hpp>
       #include <ql/patterns/visitor.hpp>
11. ql/pricingengines/
       [keep two folder , /swap and /capfloor]
      #include <ql/pricingengines/swap/discountingswapengine.hpp>
      #include <ql/pricingengines/capfloor/blackcapfloorengine.hpp>
      #include <ql/pricingengines/capfloor/analyticcapfloorengine.hpp>
      #include <ql/pricingengines/genericmodelengine.hpp>

12. ql/processes  empty 

13. ql/quotes 
        #include <ql/quotes/simplequote.hpp>

14. ql/termstructures

       ql/termstructures/credit  empty 

       ql/termstructures/inflation empty 

       ql/termstructures/volatility 
            {
            	/capfloor
            	    #include <ql/termstructures/volatility/capfloor/capfloortermvolsurface.hpp>
            	    #include <ql/termstructures/volatility/capfloor/capfloortermvolatilitystructure.hpp> 
            	/equityfx
            	    #include <ql/termstructures/volatility/equityfx/blackvoltermstructure.hpp>
            	    #include <ql/termstructures/volatility/equityfx/blackvariancecurve.hpp>
            	/inflation
            	/optionlet
            	    #include <ql/termstructures/volatility/optionlet/capletvariancecurve.hpp>
            	    #include <ql/termstructures/volatility/optionlet/optionletvolatilitystructure.hpp>
            	    #include <ql/termstructures/volatility/optionlet/optionletstripper.hpp> 
            	    #include <ql/termstructures/volatility/optionlet/strippedoptionletbase.hpp>
            	/swaption
            	     #include <ql/termstructures/volatility/swaption/swaptionvolmatrix.hpp>
            	     #include <ql/termstructures/volatility/swaption/swaptionvoldiscrete.hpp>
            	     #include <ql/termstructures/volatility/swaption/swaptionvolstructure.hpp>


            #include <ql/termstructures/volatility/volatilitytype.hpp>
             #include <ql/termstructures/volatility/volatilitytype.hpp> 
             #include <ql/termstructures/volatility/flatsmilesection.hpp>
             #include <ql/termstructures/volatility/smilesection.hpp>

            }

       ql/termstructures/yield
           {
           	 #include <ql/termstructures/yield/zerocurve.hpp>
           	 #include <ql/termstructures/yield/zeroyieldstructure.hpp
           }



15. ql/time/

    ql/time/calendars empty 
    ql/time/daycounters
       #include <ql/time/daycounters/actual365fixed.hpp>
       #include <ql/time/daycounters/actual360.hpp> 

    #include <ql/time/date.hpp>
    #include <ql/time/period.hpp>
    #include <ql/time/frequency.hpp>
     #include <ql/time/timeunit.hpp>
      #include <ql/time/weekday.hpp>
     # include <ql/time/calendar.hpp>
     #include <ql/time/businessdayconvention.hpp>
      #include <ql/time/daycounter.hpp>
      #include <ql/time/schedule.hpp>
       #include <ql/time/businessdayconvention.hpp>

16. ql/utilities/
      #include <ql/utilities/null.hpp>
       #include <ql/utilities/observablevalue.hpp>
       #include <ql/utilities/dataparsers.hpp>
        #include <ql/utilities/dataformatters.hpp> 
        #include <ql/utilities/disposable.hpp>
         #include <ql/utilities/steppingiterator.hpp> 



17. files in main folder 

 ql/option.hpp
ql/instrument.hpp
ql/errors.hpp
ql/qldefines.hpp
ql/shared_ptr.hpp
ql/types.hpp
ql/pricingengine.hpp
ql/payoff.hpp
ql/exercise.hpp
ql/settings.hpp
ql/handle.hpp
ql/termstructure.hpp
ql/interestrate.hpp
ql/version.hpp
ql/quote.hpp
ql/cashflow
ql/compounding.hpp
ql/currency.hpp
ql/discretizedasset.hpp
ql/event.hpp
ql/index.hpp
ql/numericalmethod.hpp
ql/stochasticprocess.hpp
ql/timegrid.hpp




*********************************




Now we need to consider pair cpp files !  

#include <ql/indexes/ibor/euribor.cpp>  solved.M.M.Complete
    {
    	add: ql/time/calendars/target.hpp cpp[meet,meet]
    	add: ql/currencies/europe.hpp cpp [meet,meet]

    }


#include <ql/instruments/capfloor.cpp>

     {
      #include <ql/instruments/capfloor.hpp> 
           [
            #include <ql/instrument.hpp> cpp solved. 
                (
                	 #include <ql/patterns/lazyobject.hpp> stop
                     #include <ql/pricingengine.hpp>  stop 
                     #include <ql/utilities/null.hpp> stop 
                     #include <ql/time/date.hpp>  stop 
                	)

           #include <ql/cashflows/iborcoupon.hpp> cpp solved. 
                (  
                add #include <ql/cashflows/couponpricer.hpp>
                add #include <ql/cashflows/capflooredcoupon.hpp>
                add  #include <ql/cashflows/cashflowvectors.hpp>
                   #include <ql/indexes/interestrateindex.hpp> stop 
               #include <ql/termstructures/yieldtermstructure.hpp> stop 



                	)
           #include <ql/handle.hpp> cpp  stop 
            #include <ql/termstructures/volatility/volatilitytype.hpp> stop 
           ]
      #include <ql/pricingengines/capfloor/blackcapfloorengine.hpp>
      #include <ql/pricingengines/capfloor/blackcapfloorengine.cpp>
           [add: #include <ql/pricingengines/capfloor/blackcapfloorengine.hpp>
            add: #include <ql/pricingengines/blackformula.hpp>
                  (cpp and hpp file. 
                  	#include <ql/option.hpp>
                   #include <ql/instruments/payoffs.hpp>
                   #include <ql/pricingengines/blackformula.hpp>
                  #include <ql/math/functional.hpp>
                  add:#include <ql/math/solvers1d/newtonsafe.hpp>
                   #include <ql/math/distributions/normaldistribution.hpp>



                   )
            #include <ql/termstructures/yieldtermstructure.hpp> stop 
          add: #include <ql/termstructures/volatility/optionlet/constantoptionletvol.hpp>
          add:  #include <ql/time/calendars/nullcalendar.hpp>

           ]


      add: #include <ql/pricingengines/capfloor/bacheliercapfloorengine.hpp>

           [two: 
           #include <ql/instruments/capfloor.hpp>
            #include <ql/termstructures/volatility/optionlet/optionletvolatilitystructure.hpp>
           #include <ql/pricingengines/capfloor/bacheliercapfloorengine.hpp>
           #include <ql/pricingengines/blackformula.hpp> meet
         #include <ql/termstructures/yieldtermstructure.hpp> meet
       add:  #include <ql/termstructures/volatility/optionlet/constantoptionletvol.hpp>
        add: #include <ql/termstructures/volatility/optionlet/strippedoptionletadapter.hpp>

               (
                #include <ql/termstructures/volatility/optionlet/strippedoptionletbase.hpp>
               #include <ql/termstructures/volatility/optionlet/optionletstripper.hpp>
               #include <ql/termstructures/volatility/optionlet/optionletvolatilitystructure.hpp>
               #include <ql/math/interpolation.hpp>
            add:   #include <ql/math/interpolations/sabrinterpolation.hpp>
                        {
                        add:	#include <ql/math/interpolations/xabrinterpolation.hpp>
                           #include <ql/termstructures/volatility/sabr.hpp>
                        }


               	)
         #include <ql/time/calendars/nullcalendar.hpp> meet. 


           ]
      #include <ql/math/solvers1d/newtonsafe.hpp> meet
      #include <ql/quotes/simplequote.hpp> mmet 
     add: #include <ql/cashflows/cashflows.hpp>(
     	    two: 
     	      #include <ql/cashflows/duration.hpp>

     	       #include <ql/cashflows/cashflows.hpp>
              #include <ql/cashflows/coupon.hpp>
          add:   #include <ql/termstructures/yield/flatforward.hpp>
          add:   #include <ql/math/solvers1d/brent.hpp>
           #include <ql/math/solvers1d/newtonsafe.hpp> meet
            #include <ql/cashflows/couponpricer.hpp> meet
           #include <ql/patterns/visitor.hpp> meet
            #include <ql/quotes/simplequote.hpp>
         add:    #include <ql/termstructures/yield/zerospreadedtermstructure.hpp>

     	    )
      #include <ql/utilities/dataformatters.hpp> meet
      #include <ql/termstructures/yieldtermstructure.hpp> meet 

     }




#include <ql/termstructures/yield/zerocurve.cpp>
 {
	
	#include <ql/termstructures/yield/zeroyieldstructure.hpp> stop 
    #include <ql/termstructures/interpolatedcurve.hpp>  stop 
    #include <ql/math/interpolations/linearinterpolation.hpp> stop
    #include <ql/interestrate.hpp>
    #include <ql/math/comparison.hpp>
    #include <ql/utilities/dataformatters.hpp>
}



#include <ql/termstructures/volatility/optionlet/capletvariancecurve.cpp>
#include <ql/math/optimization/levenbergmarquardt.cpp>

#include <ql/math/statistics/generalstatistics.cpp>
#include <ql/math/randomnumbers/rngtraits.cpp>
#include <ql/methods/montecarlo/multipathgenerator.cpp>

#include <ql/pricingengines/swap/discountingswapengine.cpp>
#include <ql/pricingengines/capfloor/blackcapfloorengine.cpp>
#include <ql/pricingengines/capfloor/analyticcapfloorengine.cpp>

#include <ql/models/shortrate/calibrationhelpers/caphelper.cpp>
#include <ql/models/shortrate/calibrationhelpers/swaptionhelper.cpp>

#include <ql/legacy/libormarketmodels/lfmcovarproxy.cpp>
#include <ql/legacy/libormarketmodels/lmexpcorrmodel.cpp>
#include <ql/legacy/libormarketmodels/lmlinexpcorrmodel.cpp>
#include <ql/legacy/libormarketmodels/lmfixedvolmodel.cpp>
#include <ql/legacy/libormarketmodels/lmextlinexpvolmodel.cpp>
#include <ql/legacy/libormarketmodels/liborforwardmodel.cpp>
#include <ql/legacy/libormarketmodels/lfmswaptionengine.cpp>
#include <ql/legacy/libormarketmodels/lfmhullwhiteparam.cpp>

#include <ql/time/daycounters/actual360.cpp>
#include <ql/time/schedule.cpp>
#include <ql/quotes/simplequote.cpp>


