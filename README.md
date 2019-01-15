
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

#include <ql/models/shortrate/calibrationhelpers/caphelper.hpp>
#include <ql/models/shortrate/calibrationhelpers/swaptionhelper.hpp>






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


